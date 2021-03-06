# ERC20 staking rewards distribution contracts

A generic contracts suite to bootstrap staking campaigns in which stakers get
distributed rewarded over time in relation to their share of the total staked
tokens. Supports multiple ERC20 reward tokens and locked campaigns (i.e. no
withdrawals until the end of the distribution if tokens are staked).

## Getting started

To use `defimist-erc20-staking-rewards-distribution-contracts` in your project (for
example to extend the functionality of either the distribution contract or the
factory), simply run:

```
yarn add -D `defimist-erc20-staking-rewards-distribution-contracts`
```

Built artifacts (containing ABI and bytecode) can be imported in the following
way:

```js
const erc20DistributionArtifact = require("defimist-erc20-staking-rewards-distribution-contracts/build/ERC20StakingRewardsDistribution.json");
const erc20DistributionFactoryArtifact = require("defimist-erc20-staking-rewards-distribution-contracts/build/ERC20StakingRewardsDistributionFactory.json");
```

Solidity source code can be imported in the following way:

```js
import "defimist-erc20-staking-rewards-distribution-contracts/ERC20StakingRewardsDistribution.sol";
import "defimist-erc20-staking-rewards-distribution-contracts/ERC20StakingRewardsDistributionFactory.sol";
```

## Development

Start by cloning the repo and installing dependencies by running:

```
yarn
```

To trigger a compilation run:

```
yarn compile
```

Tests will be ran using the Truffle framework. They are divided in suites
depending on contract files and execution scenarios. To trigger a test run, just
run:

```
yarn test
```

These tests won't show any coverage data. In order to show coverage statistics
collected through `solidity-coverage` another command must be launched:

```
yarn test:coverage
```

There is a third variant in the testing process that collects information about
average gas consumption and estimates the cost of calling contracts' functions
based on current gas prices read from ETHGasStation. `eth-gas-reporter` is used
to achieve this, and in order to show the aforementioned data, just run:

```
yarn test:gasreport
```

**Warning**: collecting coverage or gas consumption data while performing tests
might slow down the entire process.

Linting and "prettification" on Solidity code is performed using
`prettier-plugin-solidity` and `solhint-plugin-prettier`. Test code is simply
checked using `eslint` and `prettier`.
