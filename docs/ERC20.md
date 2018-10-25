# Standard ERC20 token
 * (ERC20.sol)

View Source: [contracts/token/ERC20/ERC20.sol](../contracts/token/ERC20/ERC20.sol)

**↗ Extends: [IERC20](IERC20.md)**
**↘ Derived Contracts: [ERC20Burnable](ERC20Burnable.md), [ERC20DetailedMock](ERC20DetailedMock.md), [ERC20Mintable](ERC20Mintable.md), [ERC20Mock](ERC20Mock.md), [ERC20Pausable](ERC20Pausable.md), [ERC20WithMetadataMock](ERC20WithMetadataMock.md), [SimpleToken](SimpleToken.md)**

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

- [totalSupply()](#totalsupply)
- [balanceOf(address owner)](#balanceof)
- [allowance(address owner, address spender)](#allowance)
- [transfer(address to, uint256 value)](#transfer)
- [approve(address spender, uint256 value)](#approve)
- [transferFrom(address from, address to, uint256 value)](#transferfrom)
- [increaseAllowance(address spender, uint256 addedValue)](#increaseallowance)
- [decreaseAllowance(address spender, uint256 subtractedValue)](#decreaseallowance)
- [_transfer(address from, address to, uint256 value)](#_transfer)
- [_mint(address account, uint256 value)](#_mint)
- [_burn(address account, uint256 value)](#_burn)
- [_burnFrom(address account, uint256 value)](#_burnfrom)

### totalSupply

⤾ overrides [IERC20.totalSupply](IERC20.md#totalsupply)

Total number of tokens in existence

```js
function totalSupply() public
returns(uint256)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### balanceOf

⤾ overrides [IERC20.balanceOf](IERC20.md#balanceof)

Gets the balance of the specified address.

```js
function balanceOf(address owner) public
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
function allowance(address owner, address spender) public
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
function transfer(address to, uint256 value) public undefined
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
function approve(address spender, uint256 value) public undefined
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
function transferFrom(address from, address to, uint256 value) public undefined
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
function increaseAllowance(address spender, uint256 addedValue) public undefined
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
function decreaseAllowance(address spender, uint256 subtractedValue) public undefined
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
function _transfer(address from, address to, uint256 value) internal undefined
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
function _mint(address account, uint256 value) internal undefined
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
function _burn(address account, uint256 value) internal undefined
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
function _burnFrom(address account, uint256 value) internal undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address | The account whose tokens will be burnt. | 
| value | uint256 | The amount that will be burnt. | 

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
