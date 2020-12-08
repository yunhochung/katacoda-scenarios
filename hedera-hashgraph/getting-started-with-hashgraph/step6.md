![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/13.png)

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/15.png)

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/14.png)

## 6.1 토픽 생성 및 Submit/Subscribe

* 파일: `consensusservice/submit_subscribe.js  `{{open}}

```javascript
// 토픽 생성
const transactionId = await new ConsensusTopicCreateTransaction().execute(myClient);
const transactionReceipt = await transactionId.getReceipt(myClient);
const topicId = transactionReceipt.getConsensusTopicId();

console.log('topid id = ', topicId);

// 메시지 수신을 위해 미러노드에 연결 후 Subscribe
const myMirrorClient = new MirrorClient('api.testnet.kabuto.sh:50211');

new MirrorConsensusTopicQuery()
    .setTopicId(topicId)
    .subscribe(
        myMirrorClient,
        (message) => console.log('<<< Received message from Mirror Node:', message.toString()),
        (error) => console.log(`Error: ${error.toString()}`));

// 메시지 송신
for (let i = 1; i < 4; i++) {
    let hcsMessage = await new ConsensusMessageSubmitTransaction().setTopicId(topicId).setMessage(`Hello, HCS! From Message ${i}`).execute(myClient);
    let hcsMessageReceipt = await hcsMessage.getReceipt(myClient);

    console.log(`>>> Sent message ${i}: ${hcsMessageReceipt.toString()}`);
}
```

* 실행

  `cd ~/meetup/202010/hands-on/getting_started/consensusservice `{{execute}}

  `node submit_subscribe.js `{{execute}}
  
* 트랜잭션 확인

  https://testnet.dragonglass.me 에서 트랜잭션을 확인합니다.

  * https://testnet.dragonglass.me/hedera/accounts/{본인 Account ID}
  * 예> https://testnet.dragonglass.me/hedera/accounts/0.0.1688


  ![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/16.png)

  

   https://explorer.kabuto.sh/testnet 에서 트랜잭션을 확인합니다.

  * https://explorer.kabuto.sh/testnet/id/{본인 Account ID}
  * 예> https://explorer.kabuto.sh/testnet/id/0.0.1688

  ![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/17.png)

  ![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/18.png)

  ![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/19.png)

