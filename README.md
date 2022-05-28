# Rainbow🌈 x Scaffold-Eth🏗️
# 🌈🏗️✨

![ezgif-2-72444e1982](https://user-images.githubusercontent.com/94156214/170820090-a46fe2c5-05e3-4583-97cc-63ece40737d7.gif)



## Typescript

This is the typescript repo of scaffold-eth and it uses `hardhat` and `vite`. The directories that you'll use are:

```bash
packages/vite-app-ts/
packages/hardhat-ts/
```

## Quick Start

Running the app

1. install your dependencies

   ```bash
   yarn install
   ```

2. start a hardhat node

   ```bash
   yarn chain
   ```

3. run the app, `open a new command prompt`

   ```bash
   # build hardhat & external contracts types
   yarn contracts:build 
   # deploy your hardhat contracts
   yarn deploy
   # start the app
   yarn start 
   ```

4. other commands
   ```bash
   # rebuild all contracts, incase of inconsistent state
   yarn contracts:rebuild
   # run hardhat commands for the workspace, or see all tasks
   yarn hardhat 'xxx'
   # run subgraph commands for the workspace
   yarn subgraph 'xxx'
   ```
## Install rainbow-kit
1. Add the dependencies

   ```bash
   yarn add @rainbow-me/rainbowkit@^0.2.0 wagmi@^0.4.2
   ```
2. Configure in App.tsx
    ```bash
    import "@rainbow-me/rainbowkit/styles.css";
   import { configureChains } from 'wagmi';
   ```
   
   ////
   
   ```bash
   import { alchemyProvider } from 'wagmi/providers/alchemy';
   const { chains, provider } = configureChains(
   [chain.mainnet, chain.polygon, chain.optimism, chain.arbitrum],
   [alchemyProvider({ alchemyId: process.env.ALCHEMY_ID })]
   ```
  
   OR

   ```bash
   import { infuraProvider } from 'wagmi/providers/infura';
   const { chains, provider } = configureChains(
   [chain.mainnet, chain.polygon, chain.optimism, chain.arbitrum],
   [infuraProvider({ infuraId: process.env.INFURA_ID })]
   ```

   OR

   ```bash
   import { publicProvider } from 'wagmi/providers/public';
   const { chains, provider } = configureChains(
   [chain.mainnet, chain.polygon],
   [publicProvider()]
   ```

   //////

   ```bash
   import {
   getDefaultWallets,
   RainbowKitProvider,
   darkTheme
   } from "@rainbow-me/rainbowkit";
   import { chain, createClient, WagmiConfig } from "wagmi";

   const { connectors } = getDefaultWallets({
     appName: "My RainbowKit App",
     chains
   });

   const wagmiClient = createClient({
     autoConnect: true,
     connectors,
     provider
   });
   ```
 3. Wrap your app
   ```bash
   const App = () => {
      return (
         <WagmiConfig client={wagmiClient}>...</WagmiConfig>
     );
   };
   ```
And you're good to go!

![Screenshot_6](https://user-images.githubusercontent.com/94156214/170820873-54e93231-d73b-4f70-b523-1609f495ab5b.png)

## Overview

Everything you need to build on Ethereum! 🚀 Quickly experiment with Solidity using a frontend that adapts to your smart contract:

![image](https://user-images.githubusercontent.com/2653167/124158108-c14ca380-da56-11eb-967e-69cde37ca8eb.png)

- 🔏 Edit your smart contract `YourContract.sol` in `packages/hardhat-ts/contracts`
- 📝 Edit your frontend `MainPage.tsx` in `packages/vite-app-ts/src`
- 💼 Edit your deployment scripts in `packages/hardhat-ts/deploy`
- 📱 Open http://localhost:3000 to see the app
- 👷🏽‍♂️ run `yarn hardhat` to get a list of all the tasks.  Run `yarn hardhat taskname` to run the task.

<br/><br/><br/>

--------------------------------------
# Guides

## Documentation

- Check out [eth-hooks docs](https://scaffold-eth.github.io/eth-hooks) for example of how to use hooks


## 🏃💨 Speedrun Ethereum
Register as a builder [here](https://speedrunethereum.com) and start on some of the challenges and build a portfolio.
>  🏁 Make sure to click on the typescript tab!

<br/><br/><br/>

--------------------------------------
# More Information!

## 📚 Documentation

Documentation, tutorials, challenges, and many more resources, visit: [docs.scaffoldeth.io](https://docs.scaffoldeth.io)

Eth-hooks documentation is [here](https://scaffold-eth.github.io/eth-hooks/).  Learn how to use the contexts here.


### 🔭 Learning Solidity

Read the docs: https://docs.soliditylang.org

Go through each topic from [solidity by example](https://solidity-by-example.org) editing `YourContract.sol` in **🏗 scaffold-eth**


## 🛠 Buidl

Check out all the [active branches](https://github.com/austintgriffith/scaffold-eth/branches/active), [open issues](https://github.com/austintgriffith/scaffold-eth/issues), and join/fund the 🏰 [BuidlGuidl](https://BuidlGuidl.com)!

[Follow the full Ethereum Speed Run](https://medium.com/@austin_48503/%EF%B8%8Fethereum-dev-speed-run-bd72bcba6a4c)

### 💬 Support Chat

Join the telegram [support chat 💬](https://t.me/joinchat/KByvmRe5wkR-8F_zz6AjpA) to ask questions and find others building with 🏗 scaffold-eth!

### 🙏🏽 Support us!

Please check out our [Gitcoin grant](https://gitcoin.co/grants/2851/scaffold-eth) too!


## 🔐 P.S.About keys

You need an RPC and API keys for testnets and production deployments, create an [Alchemy](https://www.alchemy.com/) account and replace the value of `ALCHEMY_KEY = xxx` in `packages/vite-app-ts/.env` with your new keys.

