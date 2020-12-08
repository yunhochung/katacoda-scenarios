* 파일: query-token.js  `{{open}}

```javascript
// 토큰 정보를 질의한다.
const tokenInfo = new TokenInfoQuery();
tokenInfo.setTokenId(tokenId);

const t = await tokenInfo.execute(client);
console.info(`Token Symbol: ${t.symbol}, Token Name: ${t.name}`);
console.info(`Total Supply: ${t.totalSupply}`);
console.info(`Decimals: ${t.decimals}`);
console.info(`Expiration Time: ${t.expirationTime.toDate()}`);
```

* 실행

  `cd ~/hedera-hashgraph/hedera-token-service `{{execute}}

  `node query-token.js `{{execute}}
