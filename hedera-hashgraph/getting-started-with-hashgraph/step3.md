![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/6.png)

## 3.1 Balance확인

* 파일: `cryptocurrency/getbalance.js  `{{open}}

```javascript
const HederaClient = require('./hedera-client');
const { AccountBalanceQuery } = require('@hashgraph/sdk');

async function getBalance() {
    const balance = new AccountBalanceQuery()
        .setAccountId(process.env.ACCOUNT_ID)
        .execute(HederaClient);
        
    console.log(`${HederaClient._operatorAccount} balance = ${(await balance).value()}`);
}

getBalance();
```

* 실행

  `cd ~/meetup/202010/hands-on/getting_started/cryptocurrency `{{execute}}

  `node getbalance.js `{{execute}}

## 3.2 HBar(tinybar) 송금

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/getting-started-with-hashgraph/images/7.png" alt="1" style="zoom:67%;" />

* 파일: `cryptocurrency/transferhbar.js  `{{open}}

```javascript
require('dotenv').config();
const HederaClient = require('./hedera-client');

const { Client, CryptoTransferTransaction } = require("@hashgraph/sdk");

async function transferHbar() {
    const myClient =  HederaClient; //Client.forTestnet();
    myClient.setOperator(process.env.ACCOUNT_ID, process.env.PRIVATE_KEY);

    const transactionId = await new CryptoTransferTransaction()
        .addSender(process.env.ACCOUNT_ID, 100)
        .addRecipient('0.0.3', 100)
        .execute(myClient);
    console.log('tx id:', transactionId);
    // const transactionReceipt = await transactionId.getReceipt(myClient);
    // console.log('reciept: ', transactionReceipt);

    const record = await transactionId.getRecord(myClient);
    console.log('reciept: ', record);
}

transferHbar();
```

* 실행

  `cd ~/meetup/202010/hands-on/getting_started/cryptocurrency `{{execute}}

  * 송금전 Balance 확인

  `node getbalance.js `{{execute}}

  * HBar 송금(100 tinybar)

  `node transferhbar.js `{{execute}}

  * 송금후 Balance 확인

  `node getbalance.js `{{execute}}

* 트랜잭션 확인

  https://testnet.dragonglass.me 에서 트랜잭션을 확인합니다.

  * https://testnet.dragonglass.me/hedera/accounts/{본인 Account ID}
  * 예> https://testnet.dragonglass.me/hedera/accounts/0.0.1688

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/8.png)

* 트랜잭션 수수료

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/9.png)

