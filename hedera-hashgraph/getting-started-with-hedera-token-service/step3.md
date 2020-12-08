* 파일: create-token.js  `{{open}}

```javascript
// 토큰을 생성한다.
resp = await new TokenCreateTransaction()
    .setTokenName('YH TOKEN') // 토큰명
    .setTokenSymbol('YH') // 토큰 심볼명
    .setTreasuryAccountId(client.operatorAccountId)
    .setExpirationTime(Timestamp.fromDate(Instant.now().plus(Duration.ofDays(90)).toString())) // 만기일. 90일후
    .setInitialSupply(1000000) // 토큰 갯수
    .setDecimals(0)
    .execute(client);

const tokenId = (await resp.getReceipt(client)).tokenId;

console.log('The new token ID is ' + tokenId);
```

* 실행

  `cd ~/hedera-hashgraph/hedera-token-service `{{execute}}

  `node create-token.js `{{execute}}
