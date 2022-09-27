# Overview

## Introduction

The Metaplex Protocol's Candy Machine is the leading minting and distribution program for fair NFT collection launches on Solana. It allows creators to bring their asset metadata on-chain, configure mints with anti-botting protection and whitelist tokens, and exchanges SOL or Tokens for randomized NFTs like a traditional candy machine. These  NFTs are lazy minted (=on demand) and the fees are paid by your customer. They can even automatically be added to your [Metaplex Certified Collection (MCC)](../token-metadata/certified-collections). 

By September 2022 78% of all NFT Mints in Solana were done through the Candy Machine Program. Most of the well known NFT projects launched with Metaplex candy machine, many others used forked versions of it for their mint.

## Opportunities

Candy Machine is a flexible minting program which gives you different configuration options to fit the minting experience needs of your project. Some of those more special options are explained here, you can get a detailed picture on the Configuration page *([assuming this would be created])* where you can also read how the configuration file should look like.

Those options include but are not limited to
- **Gatekeeper**: By integrating the Gatekeeper you can guard your candy machine against bots and have the minter solve a captcha before they are allowed to mint. (`Gatekeeper`)
- **Bot Protection**: Even without Gatekeeper there is a feature which taxes bots that the candy machine detects e.g. when minting too early, too late or without enough SOL. (`BotTax`)
- **Late Reveal / Hidden Settings**: Hidden settings brings the much loved functionality of reveal drops popularized by other chains such as ETH to the Solana eco system. Each of your NFTs minted from the Candy Machine will  be displayed with cover art of your choosing which enables you to then update the NFT's at a later point in time revealing all the art and attributes to your buyers and the world.
- **Whitelist**: You can whitelist users based on many different options like wallet address, proof that an NFT/Token is owned, burning or paying with NFTs / Tokens:
    - Wallet list based (`AllowList`)
    - NFT based restrict minting to holder of specific collections (`NFTGate`,`NFTBurn`, `NFTPayment`)
    - SPL Token based (`TokenGate`,`TokenBurn`, `TokenPayment`)
- **End Settings**: End your mint based on the amount of sold assets or a specific time. (`EndDate`, `RedeemedAmount`)
- **Mint Amount Restriction**: You can restrict how many NFTs a single wallet is allowed to mint. (`MintLimit`)
- **Additional Signer**: Require an additional signer in the mint TX (`ThirdPartySigner`)

## How it works

The simplified user facing process is easy. They pay the candy machine with SOL or Tokens and receive a freshly minted NFT for it:

![Image that shows the user facing process of the candy machine. It shows three different Accounts: A wallet, the Candy machine and the treasury wallet. The User wallet sends SOL or a Token to the candy machine and receives a NFT for it. The payment get's relayed from the candy machine to the treasury wallet.](/assets/programs/candy-machine/Candy-Machine-Overview-User-Facing-Process.png#radius)

Technically when using Candy Machine yourself you create an account which contains all the configuration like price and metadata. You can find more Info on the technical implementation here.

## Differences between v2 and v3

### Separation of mint logic and access control

Previous versions of the Candy Machine included access controls to limit who can mint, when minting is allowed and other settings related to the mint (e.g., price) as part of its minting procedure. While the combination of the mint logic with access controls works, this design makes it complex to add more features or to remove undesired ones.

Creating a clear separation provides a modular and flexible architechture to add and remove access control settings, whithout the risks and complexities of breaking the minting logic. Each access control logic can be implemented in isolation and users can choose to enable/disable individual ones.

## Create your own!

 The start to end from a technical point of view looks like this:

1. Create Assets like images and metadata files
2. Create the Candy Machine config file
3. Upload Assets
4. Create a new Candy Machine 
5. Write Config Lines with NFT data
6. Host a [customer facing mint website](../../guides/candy-machine-ui)
7. Start your sale

:::info
You should really use [Sugar](../../developer-tools/sugar/) for the candy machine creation which takes care of steps 2-5.
:::

## Further Information

More general information about the two Candy Machine Programs can be found here in the documentation:
* Getting Started
* Candy Core
    * Accounts
    * Instructions
* Candy Machine Configuration
* Hidden Settings
* Freeze Minted NFTs
* Support Collection NFTs
* Insert Config Lines
* Mint NFTs
* Withdraw
* FAQ
* Changelog

The most important tools for anyone who wants to use a candy machine are
* [Sugar: Candy Machine CLI](../../developer-tools/sugar/)
* [Mint UI](../../guides/candy-machine-ui)

If you want to do more with it or build your own tools you can also have a look at the features of the JS SDKs and rust crate:
* High level [JS SDK](https://github.com/metaplex-foundation/js)
* [Autogenerated API](https://www.npmjs.com/package/@metaplex-foundation/mpl-candy-machine)
* [Rust Crate](https://crates.io/crates/mpl-candy-machine)

Also feel free to Checkout the [GitHub Repository](https://github.com/metaplex-foundation/metaplex-program-library/tree/master/candy-machine) if you want to look into Candy Machines code.

