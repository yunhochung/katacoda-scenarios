화면 우측 상단에 있는 (2) 메뉴를 통해 토큰 생성(마법사)을 합니다.

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/4.png" alt="4" style="zoom:50%;" />

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/9.png" alt="9" style="zoom:50%;" />

* 1단계 - Type: Fungible 또는 Non Fungible
* 2단계 - Name: 토큰 이름, 심볼
* 3단계 - Fractional(소수점): Whole(기본값) 또는 Fractional
* 4단계 - Supply(공급량): Variable(기본값) 또는 Fixed
* 5단계 - Mutable: No 또는 Yes(기본값)
  * 토큰 상에서 수정/삭제 가능 여부
* 6단계 - KYC: No 또는 Yes(기본값)
  * 토큰 트랜잭션을 위한 계정의 KYC를 부여(Grant)하거나 폐지(Revoke) 가능 여부
* 7단계 - Wipeable: No 또는 Yes(기본값)
  * 계정의 토큰 밸런스 삭제 가능 여부
* 8단계 - Freezable: No 또는 Yes(기본값), Default(체크X)
  * 토큰 트랜잭션을 위한 계정을 동결(Freeze)하거나 해제(Unfreeze) 가능 여부
  * Hedera 계정의 동결 여부를 토큰과 관계가 있음. 값이 설정되면 토큰 수신전 계정을 해제(unfrozen)해야함.
* 9단계 - Create



이번 강좌에서 사용되는 HJ 토큰의 설정은 다음과 같습니다.

* 1단계 - Type

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/9.png" alt="9" style="zoom:50%;" />

* 2단계 - Name

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/10.png" alt="10" style="zoom:50%;" />

* 3단계 - Fractional: Whole(기본값)
* 4단계 - Supply: 초기 공급량은 **0**으로 설정

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/11.png" alt="11" style="zoom:50%;" />

* 5단계 - Mutable: Yes(기본값)
* 6단계 - KYC

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/12.png" alt="12" style="zoom:50%;" />

* 7단계 - Wipeable: Yes(기본값)
* 8단계 - Freezable: Yes(기본값), Default(체크 X)
* 9단계 - Create

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/13.png" alt="13" style="zoom:50%;" />

위 절차로 토큰을 생성하면 토큰(기본) 생성과 동일하게 화면에 아래와 같이 표시됩니다. 

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/14.png" alt="14" style="zoom:50%;" />