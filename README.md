# MarcoPolo

TradeIX and R3 launched Project [Marco Polo](https://tradeix.com/r3-tradeix-develop-blockchain-solution-open-account-trade-finance/) as a joint undertaking together with over a dozen of the world’s foremost financial institutions active in Trade Finance including BNP Paribas, Commerzbank, ING, and Natwest.

TradeIX is developing an end-to-end open account business network powered by the TIX platform and by the Corda distributed ledger technology.

The scope of the business network is pre- and post-shipment trade finance solutions including APIs and microservices, and specific applications and core technology infrastructure powered by Corda distributed ledger technology.

## Installation Guide

### Prerequisites

Before you can install the Marco Polo POC CorDapp, you will require a Corda open source or a Corda Enterprise node running on your machine and connected to a network.

R3 have provided comprehensive documentation on how to set up [Corda nodes](https://docs.corda.net/corda-nodes-index.html) and [Corda networks](https://docs.corda.net/corda-networks-index.html)

### Steps

1. Download [tradeix-concord-0.1.jar](https://github.com/TradeIX-Limited/MarcoPolo/raw/master/poc/tradeix-concord-0.1.jar) and [tradeix-concord-domain-0.1.jar](https://github.com/TradeIX-Limited/MarcoPolo/raw/master/poc/tradeix-concord-domain-0.1.jar)
2. Ensure all running java processes for the node are stopped. If you have access to the node's terminal window, typing "bye" ang hitting return should kill all processes related to the node.
3. Navigate to the `cordapps` directory where your node is installed.
4. Copy the jar files downloaded in step 1 into the `cordapps` directory.
5. Restart the Corda node and and other required processes associated with the node.
6. Once the node has restarted, you should be able to test the Marco Polo POC Vault Explorer using the url `http://<host-name>:<web-port-number>/web/tix`