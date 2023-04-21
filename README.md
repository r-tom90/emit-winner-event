# Week 4: Emit the Winner event

My goal is to Emit the winner event on this smart contract on the Goerli testnet: https://goerli.etherscan.io/address/0xcF469d3BEB3Fc24cEe979eFf83BE33ed50988502#code

Taking a look at the Code tab in Etherscan, you'll see that the source code for this contract looks like this:

```shell
// SPDX-License-Identifier: Unlicense
pragma solidity ^0.8.0;

contract Contract {
    event Winner(address);

    function attempt() external {
        require(msg.sender != tx.origin, "msg.sender is equal to tx.origin");
        emit Winner(msg.sender);
    }
}
```

This project demonstrates a basic Hardhat use case how we had to make it so the tx.origin (the EOA who originated the transaction) is not equal to the msg.sender.
