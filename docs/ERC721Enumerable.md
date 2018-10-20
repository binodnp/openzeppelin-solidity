# ERC721Enumerable.sol

**↗ Extends: [ERC165](ERC165.md), [ERC721](ERC721.md), [IERC721Enumerable](IERC721Enumerable.md)**
**↘ Derived Contracts: [ERC721Full](ERC721Full.md)**.

**ERC721Enumerable**

## Contract Members
**Constants & Variables**

```js
mapping(address => uint256[]) private _ownedTokens;
mapping(uint256 => uint256) private _ownedTokensIndex;
uint256[] private _allTokens;
mapping(uint256 => uint256) private _allTokensIndex;
bytes4 private constant _InterfaceId_ERC721Enumerable;
```

## Functions

- [tokenOfOwnerByIndex](#tokenofownerbyindex)
- [totalSupply](#totalsupply)
- [tokenByIndex](#tokenbyindex)
- [_addTokenTo](#_addtokento)
- [_removeTokenFrom](#_removetokenfrom)
- [_mint](#_mint)
- [_burn](#_burn)

### tokenOfOwnerByIndex

⤾ overrides [IERC721Enumerable.tokenOfOwnerByIndex](IERC721Enumerable.md#tokenofownerbyindex)

Gets the token ID at a given index of the tokens list of the requested owner

```js
function tokenOfOwnerByIndex(address owner, uint256 index) public view
returns(uint256)
```

**Returns**

uint256 token ID at the given index of the tokens list owned by the requested address

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| owner | address | address owning the tokens list to be accessed | 
| index | uint256 | uint256 representing the index to be accessed of the requested tokens list | 

### totalSupply

⤾ overrides [IERC721Enumerable.totalSupply](IERC721Enumerable.md#totalsupply)

Gets the total amount of tokens stored by the contract

```js
function totalSupply() public view
returns(uint256)
```

**Returns**

uint256 representing the total amount of tokens

### tokenByIndex

⤾ overrides [IERC721Enumerable.tokenByIndex](IERC721Enumerable.md#tokenbyindex)

Gets the token ID at a given index of all the tokens in this contract
Reverts if the index is greater or equal to the total number of tokens

```js
function tokenByIndex(uint256 index) public view
returns(uint256)
```

**Returns**

uint256 token ID at the given index of the tokens list

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| index | uint256 | uint256 representing the index to be accessed of the tokens list | 

### _addTokenTo

⤾ overrides [ERC721._addTokenTo](ERC721.md#_addtokento)

Internal function to add a token ID to the list of a given address
This function is internal due to language limitations, see the note in ERC721.sol.
It is not intended to be called by custom derived contracts: in particular, it emits no Transfer event.

```js
function _addTokenTo(address to, uint256 tokenId) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| to | address | address representing the new owner of the given token ID | 
| tokenId | uint256 | uint256 ID of the token to be added to the tokens list of the given address | 

### _removeTokenFrom

⤾ overrides [ERC721._removeTokenFrom](ERC721.md#_removetokenfrom)

Internal function to remove a token ID from the list of a given address
This function is internal due to language limitations, see the note in ERC721.sol.
It is not intended to be called by custom derived contracts: in particular, it emits no Transfer event,
and doesn't clear approvals.

```js
function _removeTokenFrom(address from, uint256 tokenId) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| from | address | address representing the previous owner of the given token ID | 
| tokenId | uint256 | uint256 ID of the token to be removed from the tokens list of the given address | 

### _mint

⤾ overrides [ERC721._mint](ERC721.md#_mint)

Internal function to mint a new token
Reverts if the given token ID already exists

```js
function _mint(address to, uint256 tokenId) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| to | address | address the beneficiary that will own the minted token | 
| tokenId | uint256 | uint256 ID of the token to be minted by the msg.sender | 

### _burn

⤾ overrides [ERC721._burn](ERC721.md#_burn)

Internal function to burn a specific token
Reverts if the token does not exist

```js
function _burn(address owner, uint256 tokenId) internal
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| owner | address | owner of the token to burn | 
| tokenId | uint256 | uint256 ID of the token being burned by the msg.sender | 

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
