* 파일: transfer-token.js  `{{open}}

```javascript
// 오퍼레이터 계정에서 사용중인 토큰 밸런스를 확인한다.
const query = new AccountBalanceQuery()
    .setAccountId(operatorAccount);
const tokenBalance = await query.execute(client);
console.log("The token balance(s) for operator account: " + tokenBalance.tokens + "\n");

// 수신 계정을 생성한다.
const newKey = PrivateKey.generate();

console.log('* new account')
console.log(`private key = ${newKey}`);
console.log(`public key = ${newKey.publicKey}`);

let resp = await new AccountCreateTransaction()
    .setKey(newKey.publicKey)
    .setInitialBalance(new Hbar(2))
    .execute(client);

const transactionReceipt = await resp.getReceipt(client);
const newAccountId = transactionReceipt.accountId;

console.log(`new account ID = ${newAccountId}\n`);

// 수신 계정이 토큰을 사용할 수 있도록 연결한다.
await(await(await new TokenAssociateTransaction()
    .setAccountId(newAccountId)
    .setTokenIds([tokenId])
    .freezeWith(client)
    .sign(newKey))
    .execute(client))
    .getReceipt(client);

console.log(`Associated account ${client.operatorAccountId} with token ${tokenId}`);

await(await new TokenGrantKycTransaction()
    .setAccountId(newAccountId)
    .setTokenId(tokenId)
    .execute(client))
    .getReceipt(client);

console.log(`Granted KYC for account ${newAccountId} on token ${tokenId}\n`);

// 토큰을 전송한다.
await(await new TransferTransaction()
    .addTokenTransfer(tokenId, client.operatorAccountId, -10)
    .addTokenTransfer(tokenId, newAccountId, 10)
    .execute(client))
    .getReceipt(client);

console.log(`Sent 10 tokens from account ${client.operatorAccountId} to account ${newAccountId} on token ${tokenId}`);
```

* 실행

  `cd ~/hedera-hashgraph/hedera-token-service `{{execute}}

  `node transfer-token.js `{{execute}}
