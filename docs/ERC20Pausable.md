# Pausable token (ERC20Pausable.sol)

**↗ Extends: [ERC20](ERC20.md), [Pausable](Pausable.md)**
**↘ Derived Contracts: [ERC20PausableMock](ERC20PausableMock.md)**.

**ERC20Pausable**

ERC20 modified with pausable transfers.*

## Functions

- [transfer](#transfer)
- [transferFrom](#transferfrom)
- [approve](#approve)
- [increaseAllowance](#increaseallowance)
- [decreaseAllowance](#decreaseallowance)

### transfer

⤾ overrides [ERC20.transfer](ERC20.md#transfer)

```js
function transfer(address to, uint256 value) public whenNotPaused
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| to | address |  | 
| value | uint256 |  | 

### transferFrom

⤾ overrides [ERC20.transferFrom](ERC20.md#transferfrom)

```js
function transferFrom(address from, address to, uint256 value) public whenNotPaused
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| from | address |  | 
| to | address |  | 
| value | uint256 |  | 

### approve

⤾ overrides [ERC20.approve](ERC20.md#approve)

```js
function approve(address spender, uint256 value) public whenNotPaused
returns(bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| spender | address |  | 
| value | uint256 |  | 

### increaseAllowance

⤾ overrides [ERC20.increaseAllowance](ERC20.md#increaseallowance)

```js
function increaseAllowance(address spender, uint256 addedValue) public whenNotPaused
returns(success bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| spender | address |  | 
| addedValue | uint256 |  | 

### decreaseAllowance

⤾ overrides [ERC20.decreaseAllowance](ERC20.md#decreaseallowance)

```js
function decreaseAllowance(address spender, uint256 subtractedValue) public whenNotPaused
returns(success bool)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| spender | address |  | 
| subtractedValue | uint256 |  | 

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
