Hedera 계정은 Private Key, Public Key, Account ID로 구성 되며 아래 사이트를 통해 발급 받을 수 있습니다.

- [https://portal.hedera.com](https://portal.hedera.com/)

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/getting-started-with-hashgraph/images/1.png)

회원 가입 후 실습을 위해 테스트넷(Testnet) Account를 발급 받습니다.

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/getting-started-with-hashgraph/images/2.png)

발급 받은 accountId, publicKey, privateKey 를  따로 복사해 놓습니다.

```json
{
    "operator": {
        "accountId": "0.0.1688",
        "publicKey": "302a300506032b65700321008c999110d6",
        "privateKey": "302e020100300506032b6570042204209be"
    },
    "network": {
        "0.testnet.hedera.com:50211": "0.0.3",
        "1.testnet.hedera.com:50211": "0.0.4",
        "2.testnet.hedera.com:50211": "0.0.5",
        "3.testnet.hedera.com:50211": "0.0.6"
    }
}
```
