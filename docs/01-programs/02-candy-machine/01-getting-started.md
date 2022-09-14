# Getting Started

The Candy Machine is a Solana program running on Mainnet Beta and Devnet. While you may interact with it like any other Solana program by sending transactions to a Solana node, Metaplex has built some tools to make working with it much easier. For example the CLI Tool Sugar will allow you to interact with the Candy Machine Program and the Candy Machine UI shows how to implement a mint website for your users.

## Sugar

Sugar is our new Candy Machine CLI that replaced the JavaScript CLI. It allows you to do everything with the Candy Machine that you need, from creation to asset upload, mint and at the end even destroying (withdrawing) it again. Everything it does is super fast and polished.

There are multiple resources in the official docs where you can learn more how to use sugar yourself:
- [Installation](/developer-tools/sugar/installation)
- [Quick Start](/developer-tools/sugar/quick-start) for Solana experienced developlers
- [My first Candy Machine](/developer-tools/sugar/my-first-candy-machine) for developers new to Solana 

**Additional Helpful links**
- [Github Repository](https://github.com/metaplex-foundation/sugar)
- [Releases](https://github.com/metaplex-foundation/sugar/releases)

## JavaScript SDK

When developing for the web or using [Node.js](https://nodejs.org/en/), one of the easiest ways to interact with the Candy Machine program — and other Metaplex programs — is to use our new JavaScript SDK.

It not only provides a great API to interact with programs but also abstracts away some pain points we have to deal with when interacting with the Solana blockchain. For instance, it encapsulates who is using the SDK via Identity Drivers. On top of that, the SDK was built with modularity in mind so one can easily inject plugins and modules to extend its feature set.

**The main module that interacts with the Candy Machine program is the [NFT module](https://github.com/metaplex-foundation/js-next#nfts)**. It is composed of several methods that focus on real use cases to make our life easier. Here are some of them.

```ts

```

Note that this SDK is fairly new, and we are planning on adding more methods, modules, and plugins in the future. For now, the entire documentation is written in the README of the GitHub repository. We will be writing more content as we go until the SDK is mature enough to have its own folder in this documentation.

🔗 **Helpful links:**

- [GitHub repository](https://github.com/metaplex-foundation/js-next)
- [Repository of examples using the JS SDK](https://github.com/metaplex-foundation/js-examples)
- [NPM package](https://www.npmjs.com/package/@metaplex-foundation/js-next)

## Auto-generated JavaScript library

Another way to interact with the Token Metadata program is to use its auto-generated JavaScript library. Whenever the program (written in Rust) gets updated and published, the library gets regenerated to match the latest version of the program. Note that this is what the JavaScript SDK mentioned above uses under the hood to interact with the program.

Therefore, these auto-generated libraries can be used by more advanced developers who wish to interact with the program at a lower level, i.e. by preparing instructions and sending transactions directly.

🔗 **Helpful links:**

- [GitHub repository](https://github.com/metaplex-foundation/metaplex-program-library/tree/master/token-metadata/js)
- [NPM package](https://www.npmjs.com/package/@metaplex-foundation/mpl-token-metadata)
- [API references](https://metaplex-foundation.github.io/metaplex-program-library/docs/token-metadata/index.html)

## Rust crate

If you are a Rust developer, you can also use a Rust crate to interact with the Token Metadata program. Since the program is written in Rust, this crate contains all the program's logic, including helper methods that prepare instructions for us.

This can be helpful if you are developing a Rust client or if you want to make [CPI calls](https://solanacookbook.com/references/programs.html#how-to-do-cross-program-invocation) to the Token Metadata program within your program.

🔗 **Helpful links:**

- [GitHub repository](https://github.com/metaplex-foundation/metaplex-program-library/tree/master/token-metadata/program)
- [Crate page](https://crates.io/crates/mpl-token-metadata)
- [API references](https://docs.rs/mpl-token-metadata/latest/mpl_token_metadata/)
