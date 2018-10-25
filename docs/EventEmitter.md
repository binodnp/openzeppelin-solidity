# EventEmitter.sol

View Source: [contracts/mocks/EventEmitter.sol](../contracts/mocks/EventEmitter.sol)

**EventEmitter**

**Events**

```js
event Argumentless();
event ShortUint(uint8  value);
event ShortInt(int8  value);
event LongUint(uint256  value);
event LongInt(int256  value);
event Address(address  value);
event Boolean(bool  value);
event String(string  value);
event LongUintBooleanString(uint256  uintValue, bool  booleanValue, string  stringValue);
```

## Functions

- [emitArgumentless()](#emitargumentless)
- [emitShortUint(uint8 value)](#emitshortuint)
- [emitShortInt(int8 value)](#emitshortint)
- [emitLongUint(uint256 value)](#emitlonguint)
- [emitLongInt(int256 value)](#emitlongint)
- [emitAddress(address value)](#emitaddress)
- [emitBoolean(bool value)](#emitboolean)
- [emitString(string value)](#emitstring)
- [emitLongUintBooleanString(uint256 uintValue, bool booleanValue, string stringValue)](#emitlonguintbooleanstring)
- [emitLongUintAndBoolean(uint256 uintValue, bool boolValue)](#emitlonguintandboolean)

### emitArgumentless

```js
function emitArgumentless() public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### emitShortUint

```js
function emitShortUint(uint8 value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | uint8 |  | 

### emitShortInt

```js
function emitShortInt(int8 value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | int8 |  | 

### emitLongUint

```js
function emitLongUint(uint256 value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | uint256 |  | 

### emitLongInt

```js
function emitLongInt(int256 value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | int256 |  | 

### emitAddress

```js
function emitAddress(address value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | address |  | 

### emitBoolean

```js
function emitBoolean(bool value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | bool |  | 

### emitString

```js
function emitString(string value) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| value | string |  | 

### emitLongUintBooleanString

```js
function emitLongUintBooleanString(uint256 uintValue, bool booleanValue, string stringValue) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| uintValue | uint256 |  | 
| booleanValue | bool |  | 
| stringValue | string |  | 

### emitLongUintAndBoolean

```js
function emitLongUintAndBoolean(uint256 uintValue, bool boolValue) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| uintValue | uint256 |  | 
| boolValue | bool |  | 

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
