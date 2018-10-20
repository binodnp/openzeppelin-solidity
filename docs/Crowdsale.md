# Crowdsale (Crowdsale.sol)

**↗ Extends: [ReentrancyGuard](ReentrancyGuard.md)**
**↘ Derived Contracts: [CappedCrowdsale](CappedCrowdsale.md), [MintedCrowdsale](MintedCrowdsale.md), [CrowdsaleMock](CrowdsaleMock.md), [TimedCrowdsale](TimedCrowdsale.md), [AllowanceCrowdsale](AllowanceCrowdsale.md), [IndividuallyCappedCrowdsale](IndividuallyCappedCrowdsale.md)**.

**Crowdsale**

Crowdsale is a base contract for managing a token crowdsale,
allowing investors to purchase tokens with ether. This contract implements
such functionality in its most fundamental form and can be extended to provide additional
functionality and/or custom behavior.
The external interface represents the basic interface for purchasing tokens, and conform
the base architecture for crowdsales. They are *not* intended to be modified / overridden.
The internal interface conforms the extensible and modifiable surface of crowdsales. Override
the methods to add functionality. Consider using 'super' where appropriate to concatenate
behavior.

## Contract Members
**Constants & Variables**

```js
contract IERC20 private _token;
address private _wallet;
uint256 private _rate;
uint256 private _weiRaised;
```

**Events**

```js
event TokensPurchased(address indexed purchaser, address indexed beneficiary, uint256 value, uint256 amount);
```

## Functions

- [](#)
- [token](#token)
- [wallet](#wallet)
- [rate](#rate)
- [weiRaised](#weiraised)
- [buyTokens](#buytokens)
- [_preValidatePurchase](#_prevalidatepurchase)
- [_postValidatePurchase](#_postvalidatepurchase)
- [_deliverTokens](#_delivertokens)
- [_processPurchase](#_processpurchase)
- [_updatePurchasingState](#_updatepurchasingstate)
- [_getTokenAmount](#_gettokenamount)
- [_forwardFunds](#_forwardfunds)

### 

fallback function ***DO NOT OVERRIDE***
Note that other contracts will transfer fund with a base gas stipend
of 2300, which is not enough to call buyTokens. Consider calling
buyTokens directly when purchasing tokens from a contract.

```js
function () external payable payable
```

### token

```js
function token() public view
returns(contract IERC20)
```

**Returns**

the token being sold.

### wallet

```js
function wallet() public view
returns(address)
```

**Returns**

the address where funds are collected.

### rate

⤿ Overridden Implementation(s): [IncreasingPriceCrowdsale.rate](IncreasingPriceCrowdsale.md#rate)

```js
function rate() public view
returns(uint256)
```

**Returns**

the number of token units a buyer gets per wei.

### weiRaised

```js
function weiRaised() public view
returns(uint256)
```

**Returns**

the amount of wei raised.

### buyTokens

low level token purchase ***DO NOT OVERRIDE***
This function has a non-reentrancy guard, so it shouldn't be called by
another `nonReentrant` function.

```js
function buyTokens(address beneficiary) public payable payable nonReentrant
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Recipient of the token purchase | 

### _preValidatePurchase

⤿ Overridden Implementation(s): [CappedCrowdsale._preValidatePurchase](CappedCrowdsale.md#_prevalidatepurchase),[TimedCrowdsale._preValidatePurchase](TimedCrowdsale.md#_prevalidatepurchase),[IndividuallyCappedCrowdsale._preValidatePurchase](IndividuallyCappedCrowdsale.md#_prevalidatepurchase)

Validation of an incoming purchase. Use require statements to revert state when conditions are not met. Use `super` in contracts that inherit from Crowdsale to extend their validations.
Example from CappedCrowdsale.sol's _preValidatePurchase method:
  super._preValidatePurchase(beneficiary, weiAmount);
  require(weiRaised().add(weiAmount) <= cap);

```js
function _preValidatePurchase(address beneficiary, uint256 weiAmount) internal view
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address performing the token purchase | 
| weiAmount | uint256 | Value in wei involved in the purchase | 

### _postValidatePurchase

Validation of an executed purchase. Observe state and use revert statements to undo rollback when valid conditions are not met.

```js
function _postValidatePurchase(address beneficiary, uint256 weiAmount) internal view
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address performing the token purchase | 
| weiAmount | uint256 | Value in wei involved in the purchase | 

### _deliverTokens

⤿ Overridden Implementation(s): [MintedCrowdsale._deliverTokens](MintedCrowdsale.md#_delivertokens),[AllowanceCrowdsale._deliverTokens](AllowanceCrowdsale.md#_delivertokens)

Source of tokens. Override this method to modify the way in which the crowdsale ultimately gets and sends its tokens.

```js
function _deliverTokens(address beneficiary, uint256 tokenAmount) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address performing the token purchase | 
| tokenAmount | uint256 | Number of tokens to be emitted | 

### _processPurchase

⤿ Overridden Implementation(s): [PostDeliveryCrowdsale._processPurchase](PostDeliveryCrowdsale.md#_processpurchase)

Executed when a purchase has been validated and is ready to be executed. Doesn't necessarily emit/send tokens.

```js
function _processPurchase(address beneficiary, uint256 tokenAmount) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address receiving the tokens | 
| tokenAmount | uint256 | Number of tokens to be purchased | 

### _updatePurchasingState

⤿ Overridden Implementation(s): [IndividuallyCappedCrowdsale._updatePurchasingState](IndividuallyCappedCrowdsale.md#_updatepurchasingstate)

Override for extensions that require an internal state to check for validity (current user contributions, etc.)

```js
function _updatePurchasingState(address beneficiary, uint256 weiAmount) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address receiving the tokens | 
| weiAmount | uint256 | Value in wei involved in the purchase | 

### _getTokenAmount

⤿ Overridden Implementation(s): [IncreasingPriceCrowdsale._getTokenAmount](IncreasingPriceCrowdsale.md#_gettokenamount)

Override to extend the way in which ether is converted to tokens.

```js
function _getTokenAmount(uint256 weiAmount) internal view
returns(uint256)
```

**Returns**

Number of tokens that can be purchased with the specified _weiAmount

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| weiAmount | uint256 | Value in wei to be converted into tokens | 

### _forwardFunds

⤿ Overridden Implementation(s): [RefundableCrowdsale._forwardFunds](RefundableCrowdsale.md#_forwardfunds)

Determines how ETH is stored/forwarded on purchases.

```js
function _forwardFunds() internal
```

## Contracts

- [OwnableMock](OwnableMock.md)
- [RefundableCrowdsale](RefundableCrowdsale.md)
- [ERC20SucceedingMock](ERC20SucceedingMock.md)
- [SampleCrowdsaleToken](SampleCrowdsaleToken.md)
- [PaymentSplitter](PaymentSplitter.md)
- [ERC20Migrator](ERC20Migrator.md)
- [Roles](Roles.md)
- [MerkleProof](MerkleProof.md)
- [CappedCrowdsale](CappedCrowdsale.md)
- [TokenVesting](TokenVesting.md)
- [ERC165Checker](ERC165Checker.md)
- [FinalizableCrowdsale](FinalizableCrowdsale.md)
- [IERC165](IERC165.md)
- [Arrays](Arrays.md)
- [Math](Math.md)
- [SupportsInterfaceWithLookupMock](SupportsInterfaceWithLookupMock.md)
- [IncreasingPriceCrowdsale](IncreasingPriceCrowdsale.md)
- [ERC20Pausable](ERC20Pausable.md)
- [ERC721MetadataMintable](ERC721MetadataMintable.md)
- [TokenTimelock](TokenTimelock.md)
- [MintedCrowdsale](MintedCrowdsale.md)
- [ERC721Mintable](ERC721Mintable.md)
- [ERC20Burnable](ERC20Burnable.md)
- [IERC721Receiver](IERC721Receiver.md)
- [ERC721Mock](ERC721Mock.md)
- [SafeMath](SafeMath.md)
- [IncreasingPriceCrowdsaleImpl](IncreasingPriceCrowdsaleImpl.md)
- [ReentrancyAttack](ReentrancyAttack.md)
- [MinterRoleMock](MinterRoleMock.md)
- [ReentrancyMock](ReentrancyMock.md)
- [ERC165NotSupported](ERC165NotSupported.md)
- [ERC20Mock](ERC20Mock.md)
- [AllowanceCrowdsaleImpl](AllowanceCrowdsaleImpl.md)
- [MerkleProofWrapper](MerkleProofWrapper.md)
- [SimpleToken](SimpleToken.md)
- [ERC721Enumerable](ERC721Enumerable.md)
- [ERC721FullMock](ERC721FullMock.md)
- [PauserRole](PauserRole.md)
- [CrowdsaleMock](CrowdsaleMock.md)
- [ERC165](ERC165.md)
- [ERC721Pausable](ERC721Pausable.md)
- [EventEmitter](EventEmitter.md)
- [Counter](Counter.md)
- [ERC20Mintable](ERC20Mintable.md)
- [FinalizableCrowdsaleImpl](FinalizableCrowdsaleImpl.md)
- [ERC721Burnable](ERC721Burnable.md)
- [RefundEscrow](RefundEscrow.md)
- [CapperRole](CapperRole.md)
- [IndividuallyCappedCrowdsaleImpl](IndividuallyCappedCrowdsaleImpl.md)
- [AddressImpl](AddressImpl.md)
- [SafeERC20](SafeERC20.md)
- [ERC721ReceiverMock](ERC721ReceiverMock.md)
- [ERC721PausableMock](ERC721PausableMock.md)
- [Address](Address.md)
- [CappedCrowdsaleImpl](CappedCrowdsaleImpl.md)
- [PullPayment](PullPayment.md)
- [TimedCrowdsale](TimedCrowdsale.md)
- [RefundableCrowdsaleImpl](RefundableCrowdsaleImpl.md)
- [ERC721](ERC721.md)
- [PauserRoleMock](PauserRoleMock.md)
- [ReentrancyGuard](ReentrancyGuard.md)
- [Secondary](Secondary.md)
- [TimedCrowdsaleImpl](TimedCrowdsaleImpl.md)
- [ERC165Mock](ERC165Mock.md)
- [PullPaymentMock](PullPaymentMock.md)
- [PausableMock](PausableMock.md)
- [IERC721Metadata](IERC721Metadata.md)
- [ERC20WithMetadataMock](ERC20WithMetadataMock.md)
- [MintedCrowdsaleImpl](MintedCrowdsaleImpl.md)
- [ERC721Full](ERC721Full.md)
- [Crowdsale](Crowdsale.md)
- [ERC20FailingMock](ERC20FailingMock.md)
- [ERC20BurnableMock](ERC20BurnableMock.md)
- [ConditionalEscrowMock](ConditionalEscrowMock.md)
- [SignerRole](SignerRole.md)
- [Pausable](Pausable.md)
- [Escrow](Escrow.md)
- [ArraysImpl](ArraysImpl.md)
- [ConditionalEscrow](ConditionalEscrow.md)
- [MinterRole](MinterRole.md)
- [ERC20WithMetadata](ERC20WithMetadata.md)
- [ERC721Metadata](ERC721Metadata.md)
- [ERC20PausableMock](ERC20PausableMock.md)
- [ERC165InterfacesSupported](ERC165InterfacesSupported.md)
- [ERC165CheckerMock](ERC165CheckerMock.md)
- [SignerRoleMock](SignerRoleMock.md)
- [ECDSA](ECDSA.md)
- [IERC721Full](IERC721Full.md)
- [ERC721MintableBurnableImpl](ERC721MintableBurnableImpl.md)
- [MathMock](MathMock.md)
- [ERC20Detailed](ERC20Detailed.md)
- [AllowanceCrowdsale](AllowanceCrowdsale.md)
- [PostDeliveryCrowdsaleImpl](PostDeliveryCrowdsaleImpl.md)
- [ERC721Holder](ERC721Holder.md)
- [CounterImpl](CounterImpl.md)
- [SampleCrowdsale](SampleCrowdsale.md)
- [IERC721](IERC721.md)
- [ECDSAMock](ECDSAMock.md)
- [IERC721Enumerable](IERC721Enumerable.md)
- [CapperRoleMock](CapperRoleMock.md)
- [Ownable](Ownable.md)
- [RolesMock](RolesMock.md)
- [SignatureBouncerMock](SignatureBouncerMock.md)
- [ERC20](ERC20.md)
- [IERC20](IERC20.md)
- [SignatureBouncer](SignatureBouncer.md)
- [IndividuallyCappedCrowdsale](IndividuallyCappedCrowdsale.md)
- [ERC20Capped](ERC20Capped.md)
- [ERC20DetailedMock](ERC20DetailedMock.md)
- [SafeMathMock](SafeMathMock.md)
- [ERC20MintableMock](ERC20MintableMock.md)
- [SafeERC20Helper](SafeERC20Helper.md)
- [PostDeliveryCrowdsale](PostDeliveryCrowdsale.md)
- [ERC20TokenMetadata](ERC20TokenMetadata.md)
- [SecondaryMock](SecondaryMock.md)
