# SafeERC20Helper.sol

View Source: [contracts/mocks/SafeERC20Helper.sol](../contracts/mocks/SafeERC20Helper.sol)

**SafeERC20Helper**

## Contract Members
**Constants & Variables**

```js
uint256 private _allowance;
uint256 private _allowance;
contract IERC20 private _failing;
contract IERC20 private _succeeding;

```

## Functions

- [transfer(address , uint256 )](#transfer)
- [transferFrom(address , address , uint256 )](#transferfrom)
- [approve(address , uint256 )](#approve)
- [allowance(address , address )](#allowance)
- [transfer(address , uint256 )](#transfer)
- [transferFrom(address , address , uint256 )](#transferfrom)
- [approve(address , uint256 )](#approve)
- [setAllowance(uint256 allowance_)](#setallowance)
- [allowance(address , address )](#allowance)
- [doFailingTransfer()](#dofailingtransfer)
- [doFailingTransferFrom()](#dofailingtransferfrom)
- [doFailingApprove()](#dofailingapprove)
- [doFailingIncreaseAllowance()](#dofailingincreaseallowance)
- [doFailingDecreaseAllowance()](#dofailingdecreaseallowance)
- [doSucceedingTransfer()](#dosucceedingtransfer)
- [doSucceedingTransferFrom()](#dosucceedingtransferfrom)
- [doSucceedingApprove(uint256 amount)](#dosucceedingapprove)
- [doSucceedingIncreaseAllowance(uint256 amount)](#dosucceedingincreaseallowance)
- [doSucceedingDecreaseAllowance(uint256 amount)](#dosucceedingdecreaseallowance)
- [setAllowance(uint256 allowance_)](#setallowance)
- [allowance()](#allowance)

### transfer

```js
function transfer(address , uint256 ) public undefined
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | uint256 |  | 

### transferFrom

```js
function transferFrom(address , address , uint256 ) public undefined
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | address |  | 
|  | uint256 |  | 

### approve

```js
function approve(address , uint256 ) public undefined
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | uint256 |  | 

### allowance

```js
function allowance(address , address ) public
returns(uint256)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | address |  | 

### transfer

```js
function transfer(address , uint256 ) public undefined
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | uint256 |  | 

### transferFrom

```js
function transferFrom(address , address , uint256 ) public undefined
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | address |  | 
|  | uint256 |  | 

### approve

```js
function approve(address , uint256 ) public undefined
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | uint256 |  | 

### setAllowance

```js
function setAllowance(uint256 allowance_) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| allowance_ | uint256 |  | 

### allowance

```js
function allowance(address , address ) public
returns(uint256)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
|  | address |  | 
|  | address |  | 

### doFailingTransfer

```js
function doFailingTransfer() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doFailingTransferFrom

```js
function doFailingTransferFrom() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doFailingApprove

```js
function doFailingApprove() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doFailingIncreaseAllowance

```js
function doFailingIncreaseAllowance() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doFailingDecreaseAllowance

```js
function doFailingDecreaseAllowance() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doSucceedingTransfer

```js
function doSucceedingTransfer() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doSucceedingTransferFrom

```js
function doSucceedingTransferFrom() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### doSucceedingApprove

```js
function doSucceedingApprove(uint256 amount) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| amount | uint256 |  | 

### doSucceedingIncreaseAllowance

```js
function doSucceedingIncreaseAllowance(uint256 amount) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| amount | uint256 |  | 

### doSucceedingDecreaseAllowance

```js
function doSucceedingDecreaseAllowance(uint256 amount) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| amount | uint256 |  | 

### setAllowance

```js
function setAllowance(uint256 allowance_) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| allowance_ | uint256 |  | 

### allowance

```js
function allowance() public
returns(uint256)
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
