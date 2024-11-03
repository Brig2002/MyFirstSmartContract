# SimpleStorage Smart Contract

A Solidity smart contract to manage favorite numbers, people data, and contract state. This contract provides functions for storing, retrieving, and managing numbers, names, and contract state information. It demonstrates Solidity concepts like mappings, arrays, structs, enums, events, internal/external functions, and state management.

## Prerequisites
- **MetaMask**: Install [MetaMask](https://metamask.io/) to interact with Ethereum-based applications.
- **Remix IDE**: Use [Remix IDE](https://remix.ethereum.org/) for Solidity development, compilation, and deployment.
- **GitHub Account**: Set up GitHub integration in Remix for version control and collaboration.

## Contract Structure

### State Variables
- `favoriteNumber` : A single number stored in the contract.
- `favoriteNumbers` : An array storing multiple favorite numbers.
- `people` : An array of `Person` structs, where each struct contains:
  - `name`: The person’s name.
  - `favoriteNumber`: The person’s favorite number.
- `state`: The current contract state, either `Active` or `Inactive`, managed by the `ContractState` enum.

### Mappings
- `nameToFavoriteNumber`: A mapping linking each person’s name to their favorite number.

### Functions

#### Core Functions
- `storeNumber(uint256 _favoriteNumber)`: Stores `_favoriteNumber` as `favoriteNumber`.
- `getFavoriteNumber() → uint256`: Returns the stored `favoriteNumber`.

#### Array and Struct Management
- `addFavoriteNumber(uint256 _number)`: Adds `_number` to the `favoriteNumbers` array.
- `addPerson(string _name, uint256 _favoriteNumber)`: Adds a new `Person` to the `people` array with specified `_name` and `_favoriteNumber`.

#### Utilities
- `isGreaterThan(uint256 _compareValue) → bool`: Checks if `favoriteNumber` is greater than `_compareValue` and returns `true` or `false`.
- `sumToFavoriteNumber() → uint256`: Returns the sum of integers from 1 up to `favoriteNumber`.

#### Internal and External Functions
- `internalFunction() → string`: Returns a message, callable only within this contract or derived contracts.
- `callInternalFunction() → string`: Calls `internalFunction()` and returns its message.
- `externalFunction() → string`: Returns a message, callable only from outside the contract.
- `testExternalFunction() → string`: Calls `externalFunction()` using `this` within the contract and returns its message.

#### Contract State Management
- `activateContract()`: Sets the contract’s state to `Active`.
- `deactivateContract()`: Sets the contract’s state to `Inactive`.
- `isActive() → bool`: Checks if the contract’s state is `Active` and returns `true` or `false`.

### Events
- `NumberUpdated(uint256 newNumber, address updatedBy)`: Emitted when a new `favoriteNumber` is stored.

## License
This project is licensed under the MIT License.

