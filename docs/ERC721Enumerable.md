# ERC721Enumerable.sol

View Source: [contracts/token/ERC721/ERC721Enumerable.sol](../contracts/token/ERC721/ERC721Enumerable.sol)

**↗ Extends: [ERC165](ERC165.md), [ERC721](ERC721.md), [IERC721Enumerable](IERC721Enumerable.md)**
**↘ Derived Contracts: [ERC721Full](ERC721Full.md)**

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

- [tokenOfOwnerByIndex(address owner, uint256 index)](#tokenofownerbyindex)
- [totalSupply()](#totalsupply)
- [tokenByIndex(uint256 index)](#tokenbyindex)
- [_addTokenTo(address to, uint256 tokenId)](#_addtokento)
- [_removeTokenFrom(address from, uint256 tokenId)](#_removetokenfrom)
- [_mint(address to, uint256 tokenId)](#_mint)
- [_burn(address owner, uint256 tokenId)](#_burn)

### tokenOfOwnerByIndex

⤾ overrides [IERC721Enumerable.tokenOfOwnerByIndex](IERC721Enumerable.md#tokenofownerbyindex)

Gets the token ID at a given index of the tokens list of the requested owner

```js
function tokenOfOwnerByIndex(address owner, uint256 index) public
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
function totalSupply() public
returns(uint256)
```

**Returns**

uint256 representing the total amount of tokens

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|

### tokenByIndex

⤾ overrides [IERC721Enumerable.tokenByIndex](IERC721Enumerable.md#tokenbyindex)

Gets the token ID at a given index of all the tokens in this contract
Reverts if the index is greater or equal to the total number of tokens

```js
function tokenByIndex(uint256 index) public
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
function _addTokenTo(address to, uint256 tokenId) internal undefined
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
function _removeTokenFrom(address from, uint256 tokenId) internal undefined
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
function _mint(address to, uint256 tokenId) internal undefined
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
function _burn(address owner, uint256 tokenId) internal undefined
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| owner | address | owner of the token to burn | 
| tokenId | uint256 | uint256 ID of the token being burned by the msg.sender | 

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
