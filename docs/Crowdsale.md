# Crowdsale (Crowdsale.sol)

View Source: [contracts/crowdsale/Crowdsale.sol](../contracts/crowdsale/Crowdsale.sol)

**↗ Extends: [ReentrancyGuard](ReentrancyGuard.md)**
**↘ Derived Contracts: [AllowanceCrowdsale](AllowanceCrowdsale.md), [CappedCrowdsale](CappedCrowdsale.md), [CrowdsaleMock](CrowdsaleMock.md), [IndividuallyCappedCrowdsale](IndividuallyCappedCrowdsale.md), [MintedCrowdsale](MintedCrowdsale.md), [TimedCrowdsale](TimedCrowdsale.md)**

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
event TokensPurchased(address indexed purchaser, address indexed beneficiary, uint256  value, uint256  amount);
```

## Functions

- [()](#)
- [token()](#token)
- [wallet()](#wallet)
- [rate()](#rate)
- [weiRaised()](#weiraised)
- [buyTokens(address beneficiary)](#buytokens)
- [_preValidatePurchase(address beneficiary, uint256 weiAmount)](#_prevalidatepurchase)
- [_postValidatePurchase(address beneficiary, uint256 weiAmount)](#_postvalidatepurchase)
- [_deliverTokens(address beneficiary, uint256 tokenAmount)](#_delivertokens)
- [_processPurchase(address beneficiary, uint256 tokenAmount)](#_processpurchase)
- [_updatePurchasingState(address beneficiary, uint256 weiAmount)](#_updatepurchasingstate)
- [_getTokenAmount(uint256 weiAmount)](#_gettokenamount)
- [_forwardFunds()](#_forwardfunds)

### 

fallback function ***DO NOT OVERRIDE***
Note that other contracts will transfer fund with a base gas stipend
of 2300, which is not enough to call buyTokens. Consider calling
buyTokens directly when purchasing tokens from a contract.

```js
function () external payable
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### token

```js
function token() public
returns(contract IERC20)
```

**Returns**

the token being sold.

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### wallet

```js
function wallet() public
returns(address)
```

**Returns**

the address where funds are collected.

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### rate

⤿ Overridden Implementation(s): [IncreasingPriceCrowdsale.rate](IncreasingPriceCrowdsale.md#rate)

```js
function rate() public
returns(uint256)
```

**Returns**

the number of token units a buyer gets per wei.

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### weiRaised

```js
function weiRaised() public
returns(uint256)
```

**Returns**

the amount of wei raised.

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### buyTokens

low level token purchase ***DO NOT OVERRIDE***
This function has a non-reentrancy guard, so it shouldn't be called by
another `nonReentrant` function.

```js
function buyTokens(address beneficiary) public payable nonReentrant 
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Recipient of the token purchase | 

### _preValidatePurchase

⤿ Overridden Implementation(s): [CappedCrowdsale._preValidatePurchase](CappedCrowdsale.md#_prevalidatepurchase),[IndividuallyCappedCrowdsale._preValidatePurchase](IndividuallyCappedCrowdsale.md#_prevalidatepurchase),[TimedCrowdsale._preValidatePurchase](TimedCrowdsale.md#_prevalidatepurchase)

Validation of an incoming purchase. Use require statements to revert state when conditions are not met. Use `super` in contracts that inherit from Crowdsale to extend their validations.
Example from CappedCrowdsale.sol's _preValidatePurchase method:
  super._preValidatePurchase(beneficiary, weiAmount);
  require(weiRaised().add(weiAmount) <= cap);

```js
function _preValidatePurchase(address beneficiary, uint256 weiAmount) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address performing the token purchase | 
| weiAmount | uint256 | Value in wei involved in the purchase | 

### _postValidatePurchase

Validation of an executed purchase. Observe state and use revert statements to undo rollback when valid conditions are not met.

```js
function _postValidatePurchase(address beneficiary, uint256 weiAmount) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| beneficiary | address | Address performing the token purchase | 
| weiAmount | uint256 | Value in wei involved in the purchase | 

### _deliverTokens

⤿ Overridden Implementation(s): [AllowanceCrowdsale._deliverTokens](AllowanceCrowdsale.md#_delivertokens),[MintedCrowdsale._deliverTokens](MintedCrowdsale.md#_delivertokens)

Source of tokens. Override this method to modify the way in which the crowdsale ultimately gets and sends its tokens.

```js
function _deliverTokens(address beneficiary, uint256 tokenAmount) internal undefined
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
function _processPurchase(address beneficiary, uint256 tokenAmount) internal undefined
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
function _updatePurchasingState(address beneficiary, uint256 weiAmount) internal undefined
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
function _getTokenAmount(uint256 weiAmount) internal
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
function _forwardFunds() internal undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

## Contracts

* [Address](Address.md)
* [AddressImpl](AddressImpl.md)
* [AllowanceCrowdsale](AllowanceCrowdsale.md)
* [AllowanceCrowdsaleImpl](AllowanceCrowdsaleImpl.md)
* [Arrays](Arrays.md)
* [ArraysImpl](ArraysImpl.md)
* [CappedCrowdsale](CappedCrowdsale.md)
* [CappedCrowdsaleImpl](CappedCrowdsaleImpl.md)
* [CapperRole](CapperRole.md)
* [CapperRoleMock](CapperRoleMock.md)
* [ConditionalEscrow](ConditionalEscrow.md)
* [ConditionalEscrowMock](ConditionalEscrowMock.md)
* [Counter](Counter.md)
* [CounterImpl](CounterImpl.md)
* [Crowdsale](Crowdsale.md)
* [CrowdsaleMock](CrowdsaleMock.md)
* [ECDSA](ECDSA.md)
* [ECDSAMock](ECDSAMock.md)
* [ERC165](ERC165.md)
* [ERC165Checker](ERC165Checker.md)
* [ERC165CheckerMock](ERC165CheckerMock.md)
* [ERC165InterfacesSupported](ERC165InterfacesSupported.md)
* [ERC165Mock](ERC165Mock.md)
* [ERC165NotSupported](ERC165NotSupported.md)
* [ERC20](ERC20.md)
* [ERC20Burnable](ERC20Burnable.md)
* [ERC20BurnableMock](ERC20BurnableMock.md)
* [ERC20Capped](ERC20Capped.md)
* [ERC20Detailed](ERC20Detailed.md)
* [ERC20DetailedMock](ERC20DetailedMock.md)
* [ERC20FailingMock](ERC20FailingMock.md)
* [ERC20Migrator](ERC20Migrator.md)
* [ERC20Mintable](ERC20Mintable.md)
* [ERC20MintableMock](ERC20MintableMock.md)
* [ERC20Mock](ERC20Mock.md)
* [ERC20Pausable](ERC20Pausable.md)
* [ERC20PausableMock](ERC20PausableMock.md)
* [ERC20SucceedingMock](ERC20SucceedingMock.md)
* [ERC20TokenMetadata](ERC20TokenMetadata.md)
* [ERC20WithMetadata](ERC20WithMetadata.md)
* [ERC20WithMetadataMock](ERC20WithMetadataMock.md)
* [ERC721](ERC721.md)
* [ERC721Burnable](ERC721Burnable.md)
* [ERC721Enumerable](ERC721Enumerable.md)
* [ERC721Full](ERC721Full.md)
* [ERC721FullMock](ERC721FullMock.md)
* [ERC721Holder](ERC721Holder.md)
* [ERC721Metadata](ERC721Metadata.md)
* [ERC721MetadataMintable](ERC721MetadataMintable.md)
* [ERC721Mintable](ERC721Mintable.md)
* [ERC721MintableBurnableImpl](ERC721MintableBurnableImpl.md)
* [ERC721Mock](ERC721Mock.md)
* [ERC721Pausable](ERC721Pausable.md)
* [ERC721PausableMock](ERC721PausableMock.md)
* [ERC721ReceiverMock](ERC721ReceiverMock.md)
* [Escrow](Escrow.md)
* [EventEmitter](EventEmitter.md)
* [FinalizableCrowdsale](FinalizableCrowdsale.md)
* [FinalizableCrowdsaleImpl](FinalizableCrowdsaleImpl.md)
* [IERC165](IERC165.md)
* [IERC20](IERC20.md)
* [IERC721](IERC721.md)
* [IERC721Enumerable](IERC721Enumerable.md)
* [IERC721Full](IERC721Full.md)
* [IERC721Metadata](IERC721Metadata.md)
* [IERC721Receiver](IERC721Receiver.md)
* [IncreasingPriceCrowdsale](IncreasingPriceCrowdsale.md)
* [IncreasingPriceCrowdsaleImpl](IncreasingPriceCrowdsaleImpl.md)
* [IndividuallyCappedCrowdsale](IndividuallyCappedCrowdsale.md)
* [IndividuallyCappedCrowdsaleImpl](IndividuallyCappedCrowdsaleImpl.md)
* [Math](Math.md)
* [MathMock](MathMock.md)
* [MerkleProof](MerkleProof.md)
* [MerkleProofWrapper](MerkleProofWrapper.md)
* [MintedCrowdsale](MintedCrowdsale.md)
* [MintedCrowdsaleImpl](MintedCrowdsaleImpl.md)
* [MinterRole](MinterRole.md)
* [MinterRoleMock](MinterRoleMock.md)
* [Ownable](Ownable.md)
* [OwnableMock](OwnableMock.md)
* [Pausable](Pausable.md)
* [PausableMock](PausableMock.md)
* [PauserRole](PauserRole.md)
* [PauserRoleMock](PauserRoleMock.md)
* [PaymentSplitter](PaymentSplitter.md)
* [PostDeliveryCrowdsale](PostDeliveryCrowdsale.md)
* [PostDeliveryCrowdsaleImpl](PostDeliveryCrowdsaleImpl.md)
* [PullPayment](PullPayment.md)
* [PullPaymentMock](PullPaymentMock.md)
* [ReentrancyAttack](ReentrancyAttack.md)
* [ReentrancyGuard](ReentrancyGuard.md)
* [ReentrancyMock](ReentrancyMock.md)
* [RefundableCrowdsale](RefundableCrowdsale.md)
* [RefundableCrowdsaleImpl](RefundableCrowdsaleImpl.md)
* [RefundEscrow](RefundEscrow.md)
* [Roles](Roles.md)
* [RolesMock](RolesMock.md)
* [SafeERC20](SafeERC20.md)
* [SafeERC20Helper](SafeERC20Helper.md)
* [SafeMath](SafeMath.md)
* [SafeMathMock](SafeMathMock.md)
* [SampleCrowdsale](SampleCrowdsale.md)
* [SampleCrowdsaleToken](SampleCrowdsaleToken.md)
* [Secondary](Secondary.md)
* [SecondaryMock](SecondaryMock.md)
* [SignatureBouncer](SignatureBouncer.md)
* [SignatureBouncerMock](SignatureBouncerMock.md)
* [SignerRole](SignerRole.md)
* [SignerRoleMock](SignerRoleMock.md)
* [SimpleToken](SimpleToken.md)
* [SupportsInterfaceWithLookupMock](SupportsInterfaceWithLookupMock.md)
* [TimedCrowdsale](TimedCrowdsale.md)
* [TimedCrowdsaleImpl](TimedCrowdsaleImpl.md)
* [TokenTimelock](TokenTimelock.md)
* [TokenVesting](TokenVesting.md)
