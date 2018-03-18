PRIVATESEND BASICS
====================

PrivateSend provides true financial privacy by obscuring the origins of your funds. All the WAVI in your wallet is made up of different “inputs” which you can think of as separate, discrete coins. PrivateSend makes use of an innovative process to mix your inputs with the inputs of two other people, without your coins ever leaving your wallet. You keep full control of your money at all times.

The PrivateSend process works like this:

PrivateSend starts off by breaking your transaction inputs down into standard denominations. These denominations are 0.01 WAVI, 0.1 WAVI, 1 WAVI and 10 WAVI – kind of like the paper money that you use every day.
 Your wallet then makes requests to specially configured software nodes on the network, called “masternodes”, These masternodes are then informed that you are interested in mixing a certain denomination. No identifiable information is sent to the masternodes, so they never know “who” you are.
 When two other people send similar messages, indicating that they would like to also mix the same denomination, a mixing session is started. The masternode mixes up the inputs and instructs all three users’ wallets to pay the now-transformed input back to themselves. Your wallet pays that denomination directly to itself, but in a different address (called a change address).

In order to fully obscure your funds, your wallet needs to repeat this process a number of times with each denomination. Each time the process is completed, it is called a “round”. Each round of PrivateSend makes it exponentially more difficult to determine where your funds originated from.
 This mixing process all happens in the background without any intervention on your part. When you would like to make a transaction, your funds will already be anonymized. No additional waiting is required.

IMPORTANT: Your wallet only contains 1000 of these “change addresses.” Every time a mixing event happens, one of your addresses is used up. Once enough of them are used, your wallet must create more addresses. However, it can only do this if you have enabled automatic backups. Consequently, users who have backups disabled will also have PrivateSend disabled.

Code Review K.Atlas 2014

PrivateSend Technical Details (Advanced Users)
-------------------------------------------------

PrivateSend is a unique, decentralized mixer for creating an on-demand system of removing the history from coins on the network. This is mainly for fungability, which is the attribute of money that allows any token to be exchanged with any other token, without having a difference in price in the form of a premium for tokens with less or no history. Without PrivateSend, tokens with less history would become increasingly valuable as the network grows, because of their lack of association with prior transactions. Without fungibility, there is a risk that certain tokens could be “red listed” and lose some or all of their value if at any point in the past they had been found to be used in illegal or questionable activities. Nobody wants to hold money that was involved in illegal activity, yet after the activities take place, tokens re-enter the supply and pass to new users who had no connection with the prior illegal acts. We remove this issue with the implementation of PrivateSend, which is included as part of the core protocol of the WAVI network.

PrivateSend Status Codes
--------------------------

The system has various modes which enable servers to keep track of the current state of their mixing pool. These mixing pools are single use, allowing three people to use them at a time. Statuses are idle, queued, accepting_entries, finalizing_transaction, signing_transaction and transmitting transaction.
 Users start off by connecting to a node, which is in the idle state. The masternode then moves the status to “queued” and sends a message to the network, telling other users that’s it’s currently available for mixing. Users can utilize multiple servers at a time to mix, what is called multi-session mixing. This greatly speeds up the mixing process at the cost of creating more addresses and therefore requiring more frequent wallet backups.

 

Privacy Through Ambiguity
--------------------------

Mixing is the process of joining multiple transactions together, from multiple users, where all unique information about the users is removed from the transaction. Users send tokens to themselves through the system, and at no time do these tokens ever leave the users’ wallet. masternode operators are therefore completely separate from the process of mixing. masternodes simply serve as a transit method for the storing and signing of transactions, allowing users a safe place to initiate the process in an anonymous way.
 Privacy is achieved by using denominated amounts of 100, 10, 1 or .1. Each session initiated on a masternode only carries a single denomination, such as having 10x 100 WAVI inputs and 10x 100 WAVI outputs. Users then individually sign their inputs to the collective outputs, allowing the transaction to be valid once complete and broadcastable.

Fee Model Anonymity
---------------------

In other implementations of mixing software, fees can be used to break the transactions apart and identify users on the networks. On the WAVI Network this is avoided by allowing masternodes a special type of message which allows them to broadcast fee-less transactions. We use this technology to decouple the fees from the transactions, so that for every 10 transactions using the PrivateSend technology, there is only one fee transaction. This prevents a timing attack on the PrivateSend implementation.
 Phases of PrivateSend
 The process begins when a user denominates some funds to be used as a “cash account”. They then simply tell a random masternode they would like to mix a specific denomination such as 100 WAVI. The masternode has no information about the transaction at this point, since the denomination carries no information about which inputs the user would ultimately like to mix. The masternode receives the request and issues a message to the network saying that it is ready to mix that denomination and that there is a user waiting.
 At this point if other users are wishing to mix inputs of that denomination, they can connect to the masternode that is hosting the other user’s transaction. When three users queue themselves on the same masternode, the next stage, “accepting_entries,” is initiated.

In this stage, all users send their inputs and outputs to the masternode, where they are collected and put into memory until all users have identified the full list of inputs/outputs they would like to mix. Once this is complete, the process moves onto the next stage, “finalize.” At this point, the masternode sends a message back to the users, showing the merged transaction they all jointly created. All inputs are from the user’s wallet and all outputs are sent back directly to the user’s wallet. The funds involved in this process never leave the user’s wallet at any time, allowing the masternode to be completely segregated from users’ funds. This is how the process of PrivateSend remains trustless and secure, without risking user’s funds or exposing masternodes to excessive legal risk. Once the finalized transaction is approved, the process moves onto the next phase, “signing.”

Users sign only the inputs for which they have keys, and the funds are then released to all outputs simultaneously. It’s worth noting that inputs and outputs are not directly tied to each other in this process, since inputs are in a separated list and only tied to each other. Outputs are also in a separated list, only tied to each other. This means, literally, that all users are paying all users in this process. The users are not only paying themselves, but everyone else. This means you can’t say input #4 went to output #14 (e.g. you can’t trace the input to the output, they are processed in concert).
 When all inputs are signed to all outputs, the transaction suddenly becomes valid, and the masternode broadcasts using a special message called DSTX. The network keeps track of these messages, allowing masternodes to submit one PrivateSend transaction every N hours without paying fees.
