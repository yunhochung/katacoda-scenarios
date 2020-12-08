* 파일: wipe-token.js  `{{open}}

```javascript
// 오퍼레이터 계정에서 사용중인 토큰 밸런스를 확인한다.
const query = new AccountBalanceQuery()
    .setAccountId(accountId);
let tokenBalance = await query.execute(client);
console.log("The token balance(s) for new account: " + tokenBalance.tokens + "\n");

// 계정에 설정된 토큰 밸런스를 삭제한다.
await(await new TokenWipeTransaction()
    .setTokenId(tokenId)
    .setAccountId(accountId)
    .setAmount(10)
    .execute(client))
    .getReceipt(client);

console.log(`Wiped balance of account ${accountId}\n`);

tokenBalance = await query.execute(client);
console.log("The token balance(s) for new account: " + tokenBalance.tokens + "\n");
```

* 실행

  `cd ~/hedera-hashgraph/hedera-token-service `{{execute}}

  `node wipe-token.js `{{execute}}
