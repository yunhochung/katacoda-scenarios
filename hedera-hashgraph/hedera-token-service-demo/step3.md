화면 우측 상단에 있는 (1) 메뉴를 통해 토큰 생성(기본)을 합니다.

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/4.png" alt="4" style="zoom:50%;" />

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/5.png" alt="5" style="zoom:50%;" />

* Name: 토큰 이름

* Symbol: 토큰 심볼

* Decimals: 소수점. 소수점 몇 자리까지 토큰이 분할될 수 있는지 지정. 아래 예에서는 소수점 2자리

* Initial Supply: 초기 공급량. Mint(주조) 기능을 통해 공급량 조정 가능

  * Enable Admin(adminKey): 토큰 상에서 수정/삭제 가능 여부

  * Change Supply(supplyKey): 공급량을 늘리거나(Mint) 줄이기(Burn) 가능 여부

  * Enable KYC(kycKey): 토큰 트랜잭션을 위한 계정의 KYC를 부여(Grant)하거나 폐지(Revoke) 가능 여부

  * Enable Wipe(wipeKey): 계정의 토큰 밸런스 삭제 가능 여부

  * Enable Freeze(freezeKey): 토큰 트랜잭션을 위한 계정을 동결(Freeze)하거나 해제(Unfreeze) 가능 여부

  * Default(freezeDefault): Hedera 계정의 동결 여부를 토큰과 관계가 있음. 값이 설정되면 토큰 수신전 계정을 해제(unfrozen)해야함.

    

이번 강좌에서 사용되는 YH 토큰의 설정은 다음과 같습니다.

* 토큰 이름: YH TOKEN
* 토큰 심볼: YH
* 공급량: 10000.00 (소수점 2자리)
* 속성: Admin, Change Supply, **KYC**, Wipe, Freeze 기능 사용



토큰을 생성하면 화면 하단에 아래와 같은 메시지가 출력되면서 화면에 YH 토큰이 표시됩니다.

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/6.png" alt="6" style="zoom:50%;" />

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/7.png" alt="7" style="zoom:50%;" />

