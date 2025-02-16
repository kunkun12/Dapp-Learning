[中文](https://github.com/Dapp-Learning-DAO/Dapp-Learning/main/basic/06-ethersjs-waffle/README-CN.md)

## Preface

Waffle is a smart contract test library that adapts to ehter.js. This example demonstrates the basic process and usage of Waffle test.
You can refer to the offical website of Waffle width the detailed usage(https://ethereum-waffle.readthedocs.io/en/latest/getting-started.html).If you are a developler not familiar with Waffle, you could read the sample code and do exercises, then refer to the official website for a more in-depth understanding.

## Contracts Introduction

- contract/SimpleToken.sol
  A standard ERC20 contract that implements all interface of ERC20. Users could issue ERC20 tokens using this contract.
  

## Scripts Introduction

- test/simpleTokenTest.js
  The unit test code of SimpleToken.sol contract. There is only one test script here, you could write multiple scripts of unit test codes for different contracts under the "test" directory during the development.
  Each interface of SimpleToken.sol contract will be simplely tested in the simpleTokenTest.js script.You can refer to the sample to write unit test codes of other contracts.

- index.js
  External contracts needs to be invoked separately. When unit test is passed, the script could be called to generate some actions in the production environment.

## steps

- 1 install dependencies

```bash
yarn install
```

- 2 compile contracts

```bash
yarn build
```

- 3 config environment variables

```bash
cp .env.example .env

## modify PRIVATE_KEY and INFURA_ID in .env
```

- 4 Test Execution

```bash
yarn test
```

- 5 test index.js

```bash
node index.js
```

## Note

when it hint that "cannot find yarn commands"(when running on VMWare), you can try:

1. $ sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.rep
2. $ sudo yum install yarn

check yarn version
$ yarn --versionyarn --version

- If run `yarn test` on windows, you should change the "export" keyword to the "set" keyword in the "test" command of the "scripts" key of the file named package.json

Before changed:

```
  "scripts": {
    "build": "waffle",
    "test": "export NODE_ENV=test && mocha --timeout 10000"
  },
```

afer changed:

```
  "scripts": {
    "build": "waffle",
    "test": "set NODE_ENV=test && mocha --timeout 10000"
  },
```

## Reference document


- waffle offical document: <https://ethereum-waffle.readthedocs.io/en/latest/getting-started.html>

- etherjs offical document: <https://docs.ethers.io/v4/api-providers.html>  
  <https://docs.ethers.io/v5/getting-started/#getting-started--contracts>

- Chinese document: <https://learnblockchain.cn/docs/ethers.js/api-providers.html>
