## What is Oraclum?
Oraclum is an off-chain oracle service providing signed data (e.g. prices) to be used on blockchain network (e.g. Ethereum).

## What is off-chain oracle?
An off-chain oracle is a web service providing signed data that can be verified and used by smart contracts on blockchain network. It is light, efficient, and easy to deploy. It can be used for scenarios where on-chain oracle services like Chainlink are unavailable or impractical.

## Why do we need off-chain oracle (while there is on-chain oralces like Chainlink)?
For the price feeds that are available on Chainlink with satisfactory property (e.g. deviation threshold), Chainlink would be great. However, that's not always the case. The cost of providing price feeds via on-chain oracle is significant. And that limits the availability and timeliness of the price feeds on Chainlink. You might have found a lot of wanted prices (or other market data) that are either unavailable on Chainlink or provided with a horrible deviation threshold. For example, 0.5% for ETHUSD or 1% for BNBUSD by Chainlink on Ethereum are impractical for a lot of use cases. That is when you need an off-chain oracle.

## How do I use Oraclum?
1. Deploy smart contrats expecting messages from Oraclum (see [a message example](https://api.oraclum.io/get_symbol_data?symbol=BTCUSD));
1. Inside your function, verify whether the message is signed by the [Oraclum signer](https://api.oraclum.io/get_basic_info);
1. Check if the message has expired (per your own delay allowance);
1. If the message is indeed signed by Oraclum and has not expired, then you can use its data in your smart contract.

More details can be found in the [API document](./Oraclum%20API%20Documentation.md)

## Is Oraclum centralized or decentralized?
It's a centralized service, which is why it is light, efficient, and easy to deploy. The centralized nature of Oraclum means you have to trust the signer of the oracle service.

## But why should I trust a centralized service?
While being centralized, Oraclum is completely open-sourced and fully transparent. You can see the working mechanism and the data flow crystal clear. If ever there were some do-evil action, the service would be dead immediately.

## Which blockchain networks does Oraclum work with?
Any EVM-compatible blockchain or layer2 network, e.g. Ethereum, BNB Chain, Arbitrum, Avalanche (C-Chain), etc. It even works with testnets such as Ropsten and Koven.
Technically, the only requirement is a mechanism to verfiy the signature of the message inside your smart contracts.

## What data feeds are available on Oraclum?
See this [list of supported symbols](https://api.oraclum.io/get_supported_symbols)

## Can I add/request for new data feeds that I want?
Yes. Please contact us via github.

## Is there any caveat for using Oraclum?
When your smart contract checks the validity of the message, **it must check whether it is expired**. However, due to the blockchain mechanism, there is a delay between the time point of data being signed and that of the data being checked and used by the smart contract. This delay can be exploited by attackers to front-run your smart contracts. Unfortunately, such a delay is inevitable so you have to bear with it -- set an allowance for it. But you need to be careful with the allowance. A too small allowance would increase the likelihood of your smart contract seeing an expired message and hence likelihood for the transactions to fail. Whereas, a too big allowance would increase the risk of being front-run.

**Choose your delay allowance carefully! And always take into account the delay and the associated front-run risks!**

# Disclaimer: USE ORACLUM AT YOUR OWN RISK!
**Oraclum will not be responsible for any losses, damages or claims arising from events caused by any normal or abnormal activities of Oraclum.**
