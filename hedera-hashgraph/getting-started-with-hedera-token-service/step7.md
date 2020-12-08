* 파일: delete-token.js  `{{open}}

```javascript
// 토큰 밸런스를 확인한다.
const query = new AccountBalanceQuery()
    .setAccountId(operatorAccount);
let tokenBalance = await query.execute(client);
console.log("The token balance(s) for account: " + tokenBalance.tokens + "\n");

// 토큰을 삭제한다.
await(await new TokenDeleteTransaction()
    .setTokenId(tokenId)
    .execute(client))
    .getReceipt(client);

console.log(`Deleted token ${tokenId}\n`);

tokenBalance = await query.execute(client);
console.log("The token balance(s) for account: " + tokenBalance.tokens + "\n");
```

* 실행

  `cd ~/hedera-hashgraph/hedera-token-service `{{execute}}

  `node delete-token.js `{{execute}}
