# ERC20Migrator (ERC20Migrator.sol)

View Source: [contracts/drafts/ERC20Migrator.sol](../contracts/drafts/ERC20Migrator.sol)

**ERC20Migrator**

This contract can be used to migrate an ERC20 token from one
contract to another, where each token holder has to opt-in to the migration.
To opt-in, users must approve for this contract the number of tokens they
want to migrate. Once the allowance is set up, anyone can trigger the
migration to the new token contract. In this way, token holders "turn in"
their old balance and will be minted an equal amount in the new token.
The new token contract must be mintable. For the precise interface refer to
OpenZeppelin's ERC20Mintable, but the only functions that are needed are
`isMinter(address)` and `mint(address, amount)`. The migrator will check
that it is a minter for the token.
The balance from the legacy token will be transfered to the migrator, as it
is migrated, and remain there forever.
Although this contract can be used in many different scenarios, the main
motivation was to provide a way to migrate ERC20 tokens into an upgradeable
version of it using ZeppelinOS. To read more about how this can be done
using this implementation, please follow the official documentation site of
ZeppelinOS: https://docs.zeppelinos.org/docs/erc20_onboarding.html
Example of usage:
```
const migrator = await ERC20Migrator.new(legacyToken.address);
await newToken.addMinter(migrator.address);
await migrator.beginMigration(newToken.address);
```

## Contract Members
**Constants & Variables**

```js
contract IERC20 private _legacyToken;
contract ERC20Mintable private _newToken;

```

## Functions

- [legacyToken()](#legacytoken)
- [newToken()](#newtoken)
- [beginMigration(ERC20Mintable newToken)](#beginmigration)
- [migrate(address account, uint256 amount)](#migrate)
- [migrateAll(address account)](#migrateall)

### legacyToken

Returns the legacy token that is being migrated.

```js
function legacyToken() public
returns(contract IERC20)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### newToken

Returns the new token to which we are migrating.

```js
function newToken() public
returns(contract IERC20)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### beginMigration

Begins the migration by setting which is the new token that will be
minted. This contract must be a minter for the new token.

```js
function beginMigration(ERC20Mintable newToken) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| newToken | ERC20Mintable | the token that will be minted | 

### migrate

Transfers part of an account's balance in the old token to this
contract, and mints the same amount of new tokens for that account.

```js
function migrate(address account, uint256 amount) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address | whose tokens will be migrated | 
| amount | uint256 | amount of tokens to be migrated | 

### migrateAll

Transfers all of an account's allowed balance in the old token to
this contract, and mints the same amount of new tokens for that account.

```js
function migrateAll(address account) public undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| account | address | whose tokens will be migrated | 

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
