# Standard ERC20 token  * (ERC20.sol)

**↗ Extends: [IERC20](IERC20.md)**
**↘ Derived Contracts: [ERC20Pausable](ERC20Pausable.md), [ERC20Burnable](ERC20Burnable.md), [ERC20Mock](ERC20Mock.md), [SimpleToken](SimpleToken.md), [ERC20Mintable](ERC20Mintable.md), [ERC20WithMetadataMock](ERC20WithMetadataMock.md), [ERC20DetailedMock](ERC20DetailedMock.md)**.

**ERC20**

Implementation of the basic standard token.
https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md
Originally based on code by FirstBlood: https://github.com/Firstbloodio/token/blob/master/smart_contract/FirstBloodToken.sol

## Contract Members
**Constants & Variables**

```js
mapping(address => uint256) private _balances;
mapping(address => mapping(address => uint256)) private _allowed;
uint256 private _totalSupply;
```

## Functions

- [totalSupply](#totalsupply)
- [balanceOf](#balanceof)
- [allowance](#allowance)
- [transfer](#transfer)
- [approve](#approve)
- [transferFrom](#transferfrom)
- [increaseAllowance](#increaseallowance)
- [decreaseAllowance](#decreaseallowance)
- [_transfer](#_transfer)
- [_mint](#_mint)
- [_burn](#_burn)
- [_burnFrom](#_burnfrom)

### totalSupply

⤾ overrides [IERC20.totalSupply](IERC20.md#totalsupply)

Total number of tokens in existence

```js
function totalSupply() public view
returns(uint256)
```

### balanceOf

⤾ overrides [IERC20.balanceOf](IERC20.md#balanceof)

Gets the balance of the specified address.

```js
function balanceOf(address owner) public view
returns(uint256)
```

**Returns**

An uint256 representing the amount owned by the passed address.

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| owner | address | The address to query the balance of. | 

### allowance

⤾ overrides [IERC20.allowance](IERC20.md#allowance)

Function to check the amount of tokens that an owner allowed to a spender.

```js
function allowance(address owner, address spender) public view
returns(uint256)
```

**Returns**

A uint256 specifying the amount of tokens still available for the spender.

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| owner | address | address The address which owns the funds. | 
| spender | address | address The address which will spend the funds. | 

### transfer

⤾ overrides [IERC20.transfer](IERC20.md#transfer)

⤿ Overridden Implementation(s): [ERC20Pausable.transfer](ERC20Pausable.md#transfer)

Transfer token for a specified address

```js
function transfer(address to, uint256 value) public
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| to | address | The address to transfer to. | 
| value | uint256 | The amount to be transferred. | 

### approve

⤾ overrides [IERC20.approve](IERC20.md#approve)

⤿ Overridden Implementation(s): [ERC20Pausable.approve](ERC20Pausable.md#approve)

Approve the passed address to spend the specified amount of tokens on behalf of msg.sender.
Beware that changing an allowance with this method brings the risk that someone may use both the old
and the new allowance by unfortunate transaction ordering. One possible solution to mitigate this
race condition is to first reduce the spender's allowance to 0 and set the desired value afterwards:
https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729

```js
function approve(address spender, uint256 value) public
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| spender | address | The address which will spend the funds. | 
| value | uint256 | The amount of tokens to be spent. | 

### transferFrom

⤾ overrides [IERC20.transferFrom](IERC20.md#transferfrom)

⤿ Overridden Implementation(s): [ERC20Pausable.transferFrom](ERC20Pausable.md#transferfrom)

Transfer tokens from one address to another

```js
function transferFrom(address from, address to, uint256 value) public
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| from | address | address The address which you want to send tokens from | 
| to | address | address The address which you want to transfer to | 
| value | uint256 | uint256 the amount of tokens to be transferred | 

### increaseAllowance

⤿ Overridden Implementation(s): [ERC20Pausable.increaseAllowance](ERC20Pausable.md#increaseallowance)

Increase the amount of tokens that an owner allowed to a spender.
approve should be called when allowed_[_spender] == 0. To increment
allowed value is better to use this function to avoid 2 calls (and wait until
the first transaction is mined)
From MonolithDAO Token.sol

```js
function increaseAllowance(address spender, uint256 addedValue) public
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| spender | address | The address which will spend the funds. | 
| addedValue | uint256 | The amount of tokens to increase the allowance by. | 

### decreaseAllowance

⤿ Overridden Implementation(s): [ERC20Pausable.decreaseAllowance](ERC20Pausable.md#decreaseallowance)

Decrease the amount of tokens that an owner allowed to a spender.
approve should be called when allowed_[_spender] == 0. To decrement
allowed value is better to use this function to avoid 2 calls (and wait until
the first transaction is mined)
From MonolithDAO Token.sol

```js
function decreaseAllowance(address spender, uint256 subtractedValue) public
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| spender | address | The address which will spend the funds. | 
| subtractedValue | uint256 | The amount of tokens to decrease the allowance by. | 

### _transfer

Transfer token for a specified addresses

```js
function _transfer(address from, address to, uint256 value) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| from | address | The address to transfer from. | 
| to | address | The address to transfer to. | 
| value | uint256 | The amount to be transferred. | 

### _mint

⤿ Overridden Implementation(s): [ERC20Capped._mint](ERC20Capped.md#_mint)

Internal function that mints an amount of the token and assigns it to
an account. This encapsulates the modification of balances such that the
proper events are emitted.

```js
function _mint(address account, uint256 value) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address | The account that will receive the created tokens. | 
| value | uint256 | The amount that will be created. | 

### _burn

Internal function that burns an amount of the token of a given
account.

```js
function _burn(address account, uint256 value) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address | The account whose tokens will be burnt. | 
| value | uint256 | The amount that will be burnt. | 

### _burnFrom

Internal function that burns an amount of the token of a given
account, deducting from the sender's allowance for said account. Uses the
internal burn function.

```js
function _burnFrom(address account, uint256 value) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address | The account whose tokens will be burnt. | 
| value | uint256 | The amount that will be burnt. | 

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
