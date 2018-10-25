# SignatureBouncer (SignatureBouncer.sol)

View Source: [contracts/drafts/SignatureBouncer.sol](../contracts/drafts/SignatureBouncer.sol)

**↗ Extends: [SignerRole](SignerRole.md)**
**↘ Derived Contracts: [SignatureBouncerMock](SignatureBouncerMock.md)**

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

- [_isValidSignature(address account, bytes signature)](#_isvalidsignature)
- [_isValidSignatureAndMethod(address account, bytes signature)](#_isvalidsignatureandmethod)
- [_isValidSignatureAndData(address account, bytes signature)](#_isvalidsignatureanddata)
- [_isValidDataHash(bytes32 hash, bytes signature)](#_isvaliddatahash)

### _isValidSignature

is the signature of `this + sender` from a signer?

```js
function _isValidSignature(address account, bytes signature) internal
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
function _isValidSignatureAndMethod(address account, bytes signature) internal
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
function _isValidSignatureAndData(address account, bytes signature) internal
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
function _isValidDataHash(bytes32 hash, bytes signature) internal
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
