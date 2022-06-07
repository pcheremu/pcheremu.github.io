### Is it possible to read from L1 contract state in my L2 contracts on zksync?

Solution: No. Communication between L1 and L2 is asynchronous. It means that contracts can exchange messages asynchronously, but you cannot synchronously read data of the contract state in another network. Workaround: No.


### What if someone sent USDC but paid in Ether? How can I get this info?

Solution: If you’re sending transaction and pay fee in another token. We’re sending 2 transactions: 1. First one is actual transaction but with 0 transfer fee. 2. Another transaction to your own account, with 0 amount but with transaction fee. So, you can understand fee amount and token on this second “empty” transaction. Just looked on transactions from the same block and try to find another transaction with similar batch_id, it’ll be your fee transaction. After that you can request token info, and get token decimals. Our API always return integer and you have to use decimals to get actual fee amount.


### How do you get the value of the uint32_accountId parameter, if all you know is the L1/L2 address that's trying to withdraw?

Solution: You can get accountId parameter if you make data restore or by downloading our dump file. 


### Is pending_block variable unnecessary?

The link in the code leads to an outdated commit. In the new version we have different code. All actual information is available at this link.  https://github.com/matter-labs/zksync/tree/master/docs

