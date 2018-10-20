# SignatureBouncer (SignatureBouncer.sol)

**↗ Extends: [SignerRole](SignerRole.md)**
**↘ Derived Contracts: [SignatureBouncerMock](SignatureBouncerMock.md)**.

**SignatureBouncer**

A method that uses the `onlyValidSignatureAndData` modifier must make
the _signature parameter the "last" parameter. You cannot sign a message that
has its own signature in it so the last 128 bytes of msg.data (which
represents the length of the _signature data and the _signaature data itself)
is ignored when validating. Also non fixed sized parameters make constructing
the data in the signature much more complex.
See https://ethereum.stackexchange.com/a/50616 for more details.

## Contract Members
**Constants & Variables**

```js
uint256 private constant _METHOD_ID_SIZE;
uint256 private constant _SIGNATURE_SIZE;
```

## Modifiers

- [onlyValidSignature](#onlyvalidsignature)
- [onlyValidSignatureAndMethod](#onlyvalidsignatureandmethod)
- [onlyValidSignatureAndData](#onlyvalidsignatureanddata)

### onlyValidSignature

requires that a valid signature of a signer was provided

```js
modifier onlyValidSignature(bytes signature) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| signature | bytes |  | 

### onlyValidSignatureAndMethod

requires that a valid signature with a specifed method of a signer was provided

```js
modifier onlyValidSignatureAndMethod(bytes signature) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| signature | bytes |  | 

### onlyValidSignatureAndData

requires that a valid signature with a specifed method and params of a signer was provided

```js
modifier onlyValidSignatureAndData(bytes signature) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| signature | bytes |  | 

## Functions

- [_isValidSignature](#_isvalidsignature)
- [_isValidSignatureAndMethod](#_isvalidsignatureandmethod)
- [_isValidSignatureAndData](#_isvalidsignatureanddata)
- [_isValidDataHash](#_isvaliddatahash)

### _isValidSignature

is the signature of `this + sender` from a signer?

```js
function _isValidSignature(address account, bytes signature) internal view
returns(bool)
```

**Returns**

bool

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address |  | 
| signature | bytes |  | 

### _isValidSignatureAndMethod

is the signature of `this + sender + methodId` from a signer?

```js
function _isValidSignatureAndMethod(address account, bytes signature) internal view
returns(bool)
```

**Returns**

bool

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address |  | 
| signature | bytes |  | 

### _isValidSignatureAndData

the signature parameter of the method being validated must be the "last" parameter

```js
function _isValidSignatureAndData(address account, bytes signature) internal view
returns(bool)
```

**Returns**

bool

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address |  | 
| signature | bytes |  | 

### _isValidDataHash

internal function to convert a hash to an eth signed message
and then recover the signature and check it against the signer role

```js
function _isValidDataHash(bytes32 hash, bytes signature) internal view
returns(bool)
```

**Returns**

bool

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| hash | bytes32 |  | 
| signature | bytes |  | 

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
