# Cairo Counter Smart Contract Assignment

This repository contains a template for a simple Cairo counter smart contract that can increment, decrement, and reset a value. The project uses Starknet Foundry for testing and deployment.

## Assignment Requirements

You need to implement a Counter smart contract in Cairo with the following functions:

1. `constructor(initial_count)`: Initialize the counter with a given value
2. `get_count()`: Return the current counter value
3. `increment()`: Increase the counter by 1
4. `decrement()`: Decrease the counter by 1 (should not go below 0)
5. `reset()`: Reset the counter to 0

## Setup Instructions

### Prerequisites

You'll need to install:

1. asdf (version manager)
2. Scarb (Cairo package manager)
3. Starknet Foundry (testing framework)

```bash
# Install asdf (if not already installed)
# Follow instructions from https://asdf-vm.com/guide/getting-started.html

# Verify asdf installation
asdf --version

# Install Scarb plugin for asdf
asdf plugin add scarb

# Install Scarb
asdf install scarb latest
asdf global scarb latest

# Verify Scarb installation (should be >= 2.8.5)
scarb --version

# Install Starknet Foundry plugin for asdf
asdf plugin add starknet-foundry

# Install Starknet Foundry
asdf install starknet-foundry latest
asdf global starknet-foundry latest

# Verify Starknet Foundry installation
snforge --version
```

## How to Use the Automated Code Checker

### Step 1: Fork This Repository

Create a fork of this repository to your GitHub account.

### Step 2: Implement the Counter Contract

Edit `src/counter.cairo` to implement the counter functionality according to the requirements. The current implementation already has the required functions, but you should review and potentially modify it to ensure it meets all requirements.

### Step 3: Run Tests Locally

To test your implementation locally:

```bash
# Install dependencies
scarb install

# Build the contract
scarb build

# Run tests using Starknet Foundry
snforge test
```

### Step 4: Push Your Changes

Commit and push your changes to your forked repository:

```bash
git add .
git commit -m "Implement counter contract"
git push origin main
```

### Step 5: Check Test Results

After pushing your code, the GitHub Actions workflow will automatically run. You can see the results by:

1. Going to the "Actions" tab in your GitHub repository
2. Clicking on the latest workflow run
3. Checking the logs for test results
4. Downloading the test-results artifact for a summary

## Understanding Test Results

- **Green checkmark**: All tests passed! Your implementation meets the requirements.
- **Red X**: Some tests failed. Click on the workflow run to see details about which tests failed and why.

## Test Cases

The automated checker runs the following tests:

1. **Initial Value Test**: Checks if the constructor correctly sets the initial count
2. **Increment Test**: Verifies that the increment function increases the count by 1
3. **Decrement Test**: Ensures the decrement function decreases the count by 1 and doesn't go below 0
4. **Reset Test**: Confirms that the reset function sets the count back to 0

## Project Structure

```
.
├── .github/
│   └── workflows/
│       └── starknet-foundry-test.yml  # GitHub Actions workflow
├── src/
│   ├── lib.cairo                      # Library module declaration
│   └── counter.cairo                  # Counter contract implementation
├── tests/
│   └── test_counter.cairo             # Tests for counter contract
├── Scarb.toml                         # Project configuration
└── README.md                          # This file
```

## Additional Resources

- [Cairo Book](https://book.cairo-lang.org/)
- [Starknet Book](https://book.starknet.io/)
- [Starknet Foundry Documentation](https://foundry-rs.github.io/starknet-foundry/)
- [Scarb Documentation](https://docs.swmansion.com/scarb/)