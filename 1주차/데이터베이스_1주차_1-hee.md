
# chap1. 데이터베이스 기본 개념 
## 데이터베이스란?

### 데이터베이스 정의
데이터베이스는 구조화된 정보 또는 데이터의 조직화된 모음으로서 일반적으로 컴퓨터 시스템에 전자적으로 저장됩니다 데이터베이스는 일반적으로  데이터베이스 관리 시스템(DBMS)에 의해 제어됩니다. 연결된 애플리케이션과 함께 데이터와 DBMS를 하나로 묶어 데이터베이스 시스템이라고 하며 단축하여 데이터베이스라고도 합니다.

오늘날 운영되고 있는 가장 일반적인 유형의 데이터베이스에서 데이터는 일반적으로 처리 및 데이터 쿼리를 효율적으로 수행하기 위해 일련의 테이블에서 행과 열로 모델링됩니다. 그러면 데이터에 쉽게 액세스하고 관리, 수정, 업데이트, 제어 및 구성할 수 있습니다. 대부분의 데이터베이스는 데이터 작성 및 쿼리에 SQL(Structured Query Language)을 사용합니다.

### 데이터베이스의 진화

데이터베이스는 1960년대 초에 첫 등장한 이후로 극적인 발전을 이루었습니다. 계층적 데이터베이스(일대다 관계만 허용하는 트리 형태 모델)와 네트워크 데이터베이스(다중 관계를 허용하는 보다 유연한 모델) 같은 탐색 데이터베이스는 원래 데이터 저장 및 조작에 사용된 시스템이었습니다. 이러한 초기 시스템은 간단하지만 유연성이 부족했습니다. 1980년대가 되면서  **관계형 데이터베이스**가 인기를 얻었고, 이후 1990년대에는  **객체 지향 데이터베이스**가 등장했습니다. 최근에는 인터넷의 성장으로 **비정형 데이터**의 속도 및 처리에 대한 요구가 높아지면서 이에 대한 대응책으로  NoSQL 데이터베이스가 등장했습니다. 오늘날에는  **클라우드 데이터베이스**와  **자율 운영 데이터베이스**가 데이터 수집, 저장, 관리 및 활용 방법에 있어 새로운 지평을 열고 있습니다.

### 데이터베이스와 스프레드시트의 차이점

데이터베이스와 스프레드 시트(예: Microsoft Excel) 모두 정보를 편리하게 저장할 수 있는 방법입니다. 두 기술 간의 주요 차이점은 다음과 같습니다.

-   데이터 저장 및 조작 방법
-   데이터에 액세스 할 수 있는 사람
-   저장할 수 있는 데이터 양

스프레드 시트는 원래 한명의 사용자를 위해 설계되었기 때문에 해당 사용자의 특성이 반영되어 있습니다. 매우 복잡한 데이터 조작을 수행할 필요가 없는 단일 사용자나 적은 수의 사용자에게 적합합니다. 반면 데이터베이스는 훨씬 더 방대한 양의 조직화된 정보를 보관하도록 설계되었습니다. 데이터베이스를 사용하면 여러 사용자가 동시에 매우 복잡한 로직과 언어를 사용하여 데이터에 빠르고 안전하게 액세스 및 쿼리할 수 있습니다.

## 데이터베이스 유형

데이터베이스의 유형은 매우 다양합니다. 특정 조직에 가장 적합한 데이터베이스는 데이터의 사용 방식에 따라 다릅니다.

#### 관계형 데이터베이스
-   `관계형 데이터베이스`는 1980년대를 지배했습니다. 관계형 데이터베이스의 항목은 열과 행이 있는 테이블 집합으로 구성됩니다. 관계형 데이터베이스 기술은 정형 정보에 액세스하는 가장 효율적이고 유연한 방법을 제공합니다.

#### 객체 지향 데이터베이스
-   `객체 지향 데이터베이스`의 정보는 객체 지향 프로그래밍과 마찬가지로 객체 형태로 표현됩니다.

#### 분산 데이터베이스
-   `분산 데이터베이스`는 서로 다른 사이트에 위치한 둘 이상의 파일로 구성됩니다. 데이터베이스는 물리적으로 동일한 위치에 있는 여러 컴퓨터에 저장되거나 다른 네트워크에 분산될 수 있습니다.

#### 데이터 웨어하우스
-   데이터의 중앙 저장소인 `데이터 웨어하우스`는 빠른 쿼리 및 분석을 위해 특별히 설계된 데이터베이스 유형입니다.

#### NoSQL 데이터베이스
-   `NoSQL` 또는 `비관계형 데이터베이스`를 사용하면 비정형 및 반정형 데이터를 저장하고 조작할 수 있습니다(반면에 관계형 데이터베이스에서는 데이터베이스에 삽입되는 모든 데이터의 구성 방식을 정의해야 함). 웹 애플리케이션이 보다 보편화되고 복잡해지면서 NoSQL 데이터베이스의 인기가 높아졌습니다.

#### 그래프 데이터베이스
-   `그래프 데이터베이스`는 엔티티 및 엔티티 간의 관계 측면에서 데이터를 저장합니다.
-   **OLTP 데이터베이스.**  OLTP 데이터베이스는 여러 사용자가 수행하는 많은 수의 트랜잭션을 위해 설계된 고속 분석 데이터베이스입니다.

이들은 오늘날 사용되는 수십 가지 유형의 데이터베이스 중 몇 가지에 불과합니다. 덜 일반적인 다른 데이터베이스들은 매우 구체적인 과학, 재무 또는 기타 기능에 따라 맞춤화가 됩니다. 다양한 데이터베이스 유형 외에도 기술 개발 접근 방식의 변화와 클라우드 및 자동화 같은 획기적인 기술 발전이 데이터베이스를 완전히 새로운 방향으로 이끌고 있습니다. 최신 데이터베이스로는 다음과 같은 것들이 있습니다.

#### 오픈 소스 데이터베이스
-   `오픈 소스 데이터베이스 시스템`은 소스 코드가 오픈 소스인 시스템으로, SQL 또는 NoSQL 데이터베이스가 여기에 해당됩니다.

#### 클라우드 데이터베이스
-   `클라우드 데이터베이스`는 프라이빗, 퍼블릭 또는 하이브리드 클라우드 컴퓨팅 플랫폼에 상주하는 정형 또는 비정형 데이터 모음입니다. 클라우드 데이터베이스 모델 유형으로는 기존 및 서비스형 데이터베이스(DBaaS)가 있습니다. DBaaS에서는 서비스 제공자가 관리 작업과 유지 관리를 수행합니다.

#### 다중 모델 데이터베이스
-   `다중 모델 데이터베이스`는 서로 다른 유형의 데이터베이스 모델을 단일 통합 백엔드로 결합합니다. 이는 다양한 데이터 유형을 수용할 수 있다는 것을 의미합니다.

#### 문서/JSON 데이터베이스
-   문서 지향 정보를 저장, 검색 및 관리하도록 설계된  `문서 데이터베이스`는 행과 열이 아닌 JSON 형식으로 데이터를 저장하는 최신 방식입니다.

#### 자율 운영 데이터베이스
-   가장 획기적인 최신 유형의 데이터베이스인 `자율구동 데이터베이스`(자율운영 데이터베이스라고도 함)는 클라우드를 기반으로 하며, 머신러닝을 사용하여 데이터베이스 튜닝, 보안, 백업, 업데이트 및 기타 데이터베이스 관리자가 전통적으로 수행해 온 일상적인 관리 작업을 자동화합니다.



## 데이터베이스 유형에 따른 서비스 종류
| Database 분류 | 서비스 종류 |
|---|---|
|관계형 데이터베이스(relational database management system) | MySQL, PostgreSQL, MariaDB, Microsoft SQL Server, Oracle Database |
| 객체 지향 데이터베이스(object oriented database) | MongoDB |
| 분산 데이터베이스(distributed database) | Apache Ignite, Apache Cassandra, AWS SimpleDB 등 |
| 데이터 웨어하우스(data warehouse) | Snowflake, Google BigQuery, Amazon Redshift, Azure Synapse Analytics, IBM Db2 Warehouse, Firebolt |
| NoSQL 데이터베이스(NoSQL database) | MongoDB, Apache CouchDB, Oracle NoSQL Database, Riak, Objectivity InfiniteGraph, Takeaway |
| 그래프 데이터베이스(graph) | neo4j, RedisGraph, OrientDB |
| 오픈 소스 데이터베이스(open source database) | PostgreSQL, MariaDB, CockroachDB, Neo4j| 
| 클라우드 데이터베이스(cloud database) | AWS, Oracle Database, Microsoft Azure, Google Cloud Platform, IBM DB2, MongoDB Atlas, OpenStack |
| 다중 모델 데이터베이스(multi model database) | MarkLogic, ArangoDB, OrientDB, Azure Cosmos DB, FoundationDB, Couchbase, Apache Ignite|
| 문서 데이터베이스(document oriented database) | MongoDB, DynamoDB, CosmosDB |
| JSON 데이터베이스 (JSON databases) | MongoDB, Cosmos DB, CouchDB, Couchbase, Firestore | 
| 자율 운영 데이터베이스(Autonomous Database) |  Oracle Autonomous Database |


# chap 2. 데이터베이스 언어 (SQL, DDL, DML, DCL) 
### SQL이란?
SQL 문을 사용하여 데이터베이스에서 정보를 저장, 업데이트, 제거, 검색 및 검색하기 위한 질의어
<U>Structured query language (SQL) is a programming language for storing and processing information in a relational database</U>

### 데이터 정의어 (DDL, Data Definition Language)
→ 데이터 생성, 수정, 삭제

| DDL | 설명 |
|---|---|
| CREATE | 데이터베이스, 테이블 등을 생성 |
| ALTER | 테이블 수정 |
| DROP | 데이터베이스, 테이블을 삭제 |
| TRUNCATE | 테이블 초기화 |

### 데이터 조작어 (DML, Data Manipulation Language)
→ 데이터 조회, 삽입, 수정, 삭제

| DDL | 설명 |
|---|---|
| SELECT | 데이터 조회 |
| INSERT | 데이터 삽입 |
| UPDATE | 데이터 수정 |
| DELETE | 데이터 삭제 |

### 데이터 제어어 (DCL, Data Control Language)
→ 데이터베이스에 대한 접근 권한 등을 하는 역할을 갖는 언어

| DCL | 설명 |
|---|---|
| GRANT | 특정 데이터베이스 사용자에 대한 작업 수행 권한 |
| REVOKE | 특정 데이터베이스 사용자에게 특정 작업에 대한 권한을 박탈, 회수 |
| COMMIT | 트랜잭션의 세이브포인트, 트랜잭션이 완료됨을 관리자에게 알려줌 |
| ROLLBACK | 트랜잭션 작업을 복구 |


# Chap3. RDBMS와 NoSql 
## RDMBS란? 
 관계형 데이터베이스란 데이터가 하나 이상의 열과 행의 테이블(또는 '관계')에 저장되어 서로 다른 데이터 구조가 어떻게 관련되어 있는지 쉽게 파악하고 이해할 수 있도록 사전 정의된 관계로 데이터를 구성하는 정보 모음이다.

1970년대 IBM의 EF Codd가 개발한 관계형 데이터베이스 모델을 사용하면 모든 테이블을 공통 속성을 사용해 다른 테이블과 연관시킬 수 있습니다. Codd는 계층 구조를 사용하여 데이터를 정리하는 대신 데이터가 포함된 테이블을 재구성하지 않고 테이블에 데이터가 저장, 액세스 및 연결되는 데이터 모델을 사용하는 것으로 전환할 것을 제안했습니다.

관계형 데이터베이스는 비즈니스에서 데이터를 구성, 관리, 연결하는 데 도움이 되는 스프레드시트 파일 모음이라고 생각하면 됩니다. 관계형 데이터베이스 모델에서 각 '스프레드시트'는 열(속성)과 행(레코드 또는  _튜플_)으로 대표되는 정보를 저장하는 테이블입니다.

속성(열)은 데이터 유형을 지정하며 각 레코드(또는 행)는 구체적인 데이터 유형의 값을 포함합니다. 관계형 데이터베이스의 모든 테이블에는 행에서 고유하게 식별 가능한  **기본 키**라는 속성이 있으며,  **외래 키**(다른 기존 테이블의 기본 키를 참조)를 사용하여 각 행에서 서로 다른 테이블 간의 관계를 만드는 데 사용할 수 있습니다.

#### 관계형 데이터베이스의 핵심은 `관계(Relation)`, 따라서 이러한 관계를 형성하기 위해서 필수적인 개념인 `기본키(Primary key)`와 `외래키(Foreign Key)`가 매우 중요하다.

## NoSql이란? 
NoSQL 데이터베이스는 특정 데이터 모델에 대해 특정 목적에 맞추어 구축되는 데이터베이스로서 현대적인 애플리케이션 구축을 위한 유연한 스키마를 갖추고 있습니다. NoSQL 데이터베이스는 개발의 용이성, 기능성 및 확장성을 널리 인정받고 있습니다. 이 페이지에는 NoSQL 데이터베이스를 보다 잘 이해하고 효과적으로 시작할 수 있도록 지원할 리소스가 포함합니다.




## NoSQL(비관계형) 데이터베이스의 작동 방식

NoSQL 데이터베이스에서는 데이터의 액세스 및 관리를 위해 다양한 데이터 모델을 사용합니다. 이러한 데이터베이스 유형은 큰 테이터 볼륨, 짧은 지연 시간과 유연한 데이터 모델이 필요한 애플리케이션에 최적화되었으며, 이는 다른 데이터베이스의 데이터 일관성 제약 일부를 완화함으로써 이루어집니다.

간단한 서적 데이터베이스를 위한 스키마 모델 구축 사례를 고려해 봅시다:

-   관계형 데이터베이스에서, 서적 레코드는 흔히 숨겨져(또는 "정규화되어") 별도의 테이블에 보관되고, 관계는 기본 및 외래 키 제약 조건으로 정의됩니다. 이 예시에서  **서적** 테이블에는  **ISBN**,  **책 제목**, 및  **에디션 번호**  열이 있으며,  **저자** 테이블에는  **저자 ID**  및  **저자명**  열이 있고, 마지막으로  **저자-ISBN**  테이블에는  **저자 ID**  및  **ISBN**  열이 있습니다. 관계형 모델은 중복성을 줄이도록 정규화되고 일반적으로 저장에 최적화된 데이터베이스에서 데이터베이스가 테이블 사이에서 참조 무결성을 실현할 수 있도록 고안되었습니다.  
    
-   NoSQL 데이터베이스에서, 서적 레코드는 보통  JSON 문서로 저장됩니다. 각각의 서적에 대해, 항목,  **ISBN**,  **책제목**,  **에디션 번호**,  **저자명**, 및  **저자 ID**가 단일 문서 내에 속성으로 저장됩니다. 이 모델에서, 데이터는 직관적 개발과 수평 확장성에 최적화됩니다.

# NoSQL 데이터베이스를 사용해야 하는 이유

NoSQL 데이터베이스는 탁월한 사용자 경험을 제공하기 위하여 유연성과 확장성을 비롯해 고성능의 매우 기능적인 데이터베이스를 필요로 하는 모바일, 웹이나 게이밍과 같은 다양한 현대적인 애플리케이션에 적합합니다.

-   **유연성:** NoSQL 데이터베이스는 일반적으로 유연한 스키마를 제공하여 보다 빠르고 반복적인 개발을 가능하게 해줍니다. 이같은 유연한 데이터 모델은 NoSQL 데이터베이스를 반정형 및 비정형 데이터에 이상적으로 만들어 줍니다.
-   **확장성:** NoSQL 데이터베이스는 일반적으로 고가의 강력한 서버를 추가하는 대신 분산형 하드웨어 클러스터를 이용해 확장하도록 설계되었습니다. 일부 클라우드 제공자들은 완전관리형 서비스로서 이런 운영 작업을 보이지 않게 처리합니다.
-   **고성능:** NoSQL 데이터베이스는 특정 데이터 모델 및 액세스 패턴에 대해 최적화되어 관계형 데이터베이스를 통해 유사한 기능을 충족하려 할 때보다 뛰어난 성능을 얻게 해줍니다.
-   **고기능성:** NoSQL 데이터베이스는 각 데이터 모델에 맞춰 특별히 구축된 뛰어난 기능의 API와 데이터 유형을 제공합니다.


# Chap 4. 인덱스(Index)
## 인덱스(index)
데이터베이스에서 추가적인 쓰기 작업 공간을 활용하여 데이터베이스 테이블의 검색 속도를 향상시키기 위한 자료구조
도서의 목차처럼 데이터베이스 내부의 데이터를 빠르게 찾는 데 의의가 있음

#### 인덱스는 SQL문을 통해 추가(INSERT), 삭제(DELETE), 수정(UPDATE) 할 수 있음

### 인덱스의 장점과 단점
#### 장점
- 테이블을 조회하는 속도와 성능을 향상
- 전반적인 시스템의 부하 감소
#### 단점
- 인덱스를 관리하기 위해 DB의 약 10% 저장공간 필요
- 인덱스를 관리하기 위해 추가작업 필요
- 인덱스가 만능은 아니다, 잘못 사용하면 오히려 성능이 저하될 수 있다.

### 인덱스를 사용하기 좋은 경우
- 규모가 큰 데이터 테이블
- INSERT, UPDATE, DELETE가 자주 발생하지 않는 칼럼
- JOIN, WHERE 또는 ORDER BY 절에 자주 사용되는 칼럼
- 데이터의 중복이 낮은 컬럼
	→ 성별 칼럼 같은 경우, index 도입 안 하는 편이 나음


## 인덱스의 자료구조
### 1.  해시테이블(Hash  Table)
- key-value 쌍으로 데이터를 저장하는 자료구조, 빠른 데이터 검색이 필요할 때 유용
- key-value 쌍으로 검색하므로 시간복잡도가 O(1)이고 매우 빠름
- 등호 연산(=) 으로 데이터베이스를 많이 조회하는 경우에 좋음
- 부등호 연산으로 데이터베이스를 조회하는 경우에는 부적합하여 많이 사용되는 자료구조는 아닌 편이다.

### 2. B+ Tree
B- Tree를 개선시킨 자료구조로써 다음과 같은 특징을 가짐
- 리프노드(데이터 노드)만 인덱스와 함께 데이터(Value)를 가지고 있고, 나머지 노드(Index Node)들은 데이터를 위한 인덱스(Key)만을 갖는다.
- 리프 노드들은 연결리스트(LinkedList)로 연결되어 있다.
- 데이터 노드 크기는 인덱스 노드의 크기와 같지 않아도 된다.

#### 검색 시 무조건 리프노드까지 가는 특징이 있음.
- B+ Tree는 O(Log2N)의 시간복잡도를 갖지만, 해시 테이블보다 인덱싱에 더 적합한 자료구조가 됨.


# Chap 5. 정규화(Normalization)와 반정규화(De-Normalization)

## 정규화(Normalization)란?
-   정규화는 데이터의 일관성, 최소한의 데이터 중복, 최소한의 데이터 유연성을 위한 방법이며 데이터를 분해하는 과정이다.
-   정규화된 모델은 테이블이 분해된다. 테이블이 분해되면 직원 테이블과 부서 테이블 간에 부서코드로 조인(join)을 수행하며 하나의 합집합으로 만들 수 있다.
-   정규화를 하면 불필요한 데이터를 입력하지 않아도 되기 때문에  **중복 데이터가 제거**된다.

## 정규화의 과정
#### 제1정규화
- 속성(Attribute)의 **원자성**을 확보한다.
- 속성의 **중복값을 제거**한다.
- 기본키(Primary key)를 설정한다.

#### 제2정규화
- 기본키가 2개 이상으로 속성으로 이루어진 경우, **부분 함수 종속성**을 제거(분해)한다.
- 부분 함수 종속성이란, 기본키가 2개 이상인 칼럼으로 이루어진 경우에만 발생
- 복합 인스턴스에 대해 **각 인스턴스의 종속적 중복**을 삭제

#### 제3정규화
- 기본키를 제외한 칼럼 간에 종속성을 제거한다.
- *`이행 함수 종속성`을 제거한다.
- 일반 속성의 종속성을 제거한다.

**이행 함수 종속성** : 릴레이션에서 X, Y, Z라는 3 개의 속성이 있을 때 X→Y, Y→Z 이란 종속 관계가 있을 경우, X→Z가 성립될 때 이행적 함수 종속이라고 한다.

#### BCNF 
- 기본키를 제외하고 후보키가 있는 경우, 후보키가 기본키를 종속시키면 분해
- BCNF는 복수의 후보키가 있고, 후보키들이 **복합 속성**이어야 하며, 서로 중첩되어야 한다.

#### 제4정규화
- 여러 칼럼들이 하나의 칼럼을 종속시키는 경우, 분해하여 다중값 종속성을 제거한다.
- **다치 종속성**을 제거한다.

**다치 종속성** :  릴레이션 내의 두 어트리뷰트 집합 사이 성립하는 제약조건, 어떠한 조건을 만족하는 투플이 릴레이션 안에 있을 것을 요구한다. 그러므로 다치 종속은 튜플이 만들어내는 "종속" 중의 한 종류로 분류

#### 다치 종속성에 대한 설명
https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=myung_aoul&logNo=140029654106

#### 제5정규화
- 조인에 의해서 종속성이 발생되는 경우 분해한다.

## 정규화의 장점과 단점
### 정규화의 장점
- 조인으로 인해 성능이 저하되는 문제를 해결할 수 있다.
- 데이터의 중복을 제거할 수 있다.


### 정규화의 단점
- 정규화는 데이터 조회(SELECT) 시 조인(JOIN)을 유발시키기 때문에 CPU와 메모리를 많이 소비한다.
- JOIN이 증가하여 오히려 성능이 떨어질 수도 있다.

## 반정규화(De-Normalization)란?
데이터베이스의 성능향상을 위해, 데이터의 중복을 허용하고 조인을 줄이는 데이터베이스 성능 향상 기법 ( → 정규화의 역과정)
반정규화는 조회(SELECT) 속도를 향상 시키지만 모델의 유연성은 낮아진다.

### 반정규화를 하는 이유
- 정규화에 충실했지만, 데이터 조회 등의 작업 속도에 영향을 주는 경우
- 많은 범위를 갖는 데이터를 자주 처리하는 경우
- 특정 범위의 데이터만 자주 처리하는 경우
- 요약/집계 정보가 자주 요구되는 경우

## 반정규화의 과정
#### 대상 조사 및 검토
- 데이터 처리 범위, 통계성 등을 확인하여 반정규화  대상을 조사

#### 다른 방법 검토
- 반 정규화 수행 전, 다른 방법이 없는지 검토
- 클러스터링, 뷰, 인덱스 튜닝, 응용프로그램, 파티션의 경우의 수 검토

#### 반정규화 수행
- 테이블, 속성, 관계 등을 반정규화 함

**클러스터링(Clustering)?**
- 인덱스 정보 저장 시 물리적으로 정렬하여 저장하는 기법
- 조회 시 인접 블록을 연속적으로 읽기 때문에 성능을 향상시킴

## 반정규화의 기법
#### 계산된 컬럼 추가
- 배치 프로그램으로 통계 데이터 등을 계산하여 특정 칼럼에 추가함

####  테이블 수직 분할
- 하나의 테이블을 두개 이상의 테이블로 분할

#### 테이블 수평 분할
- 하나의 테이블에 있는 값을 기준으로 테이블을 분할

```java
Partition
- 데이터베이스에서 파티션을 사용하여 테이블을 분할할 수 있다. 
- 파티션을 사용하면 논리적으로는 하나의 테이블이지만, 여러 개의 데이터 파일에 분산되어 저장된다. 
- Range  Partition: 데이터 값의 범위를 기준으로 파티션을 수행한다. 
- List Partition: 특정한 값을 지정하여 파티션을 수행한다. 
- Hash Partition: 해시 함수를 적용하여 파티션을 수행한다. 
- Composite Partition: 범위와 해시를 복합적으로 사용하여 파티션을 수행한다.
```

# Chap6. 트랜잭션
## 트랜잭션(Transaction)이란?
- 트랜잭션(Transaction)이란, 데이터베이스의 상태를 변화 시키기 위해 수행하는 작업의 단위
- 쪼갤 수 없는 업무 처리의 최소 단위

### 트랜잭션을 사용하는 이유
- 은행에서 돈을 출금/송금하는 경우 둘 중 어느 하나라도 정확하게 이루어지지 않으면 해당 거래는 치명적인 오류와 문제를 발생 시킴
- 대규모의 데이터를 다루는 작업을 하는 경우 중간에 시스템 오류로 비정상 종료될 경우 최소한의 백업 데이터를 보존하기 위한 전략

#### 트랜잭션의 예시
```mysql
-- 트랜잭션 시작 
START TRANSACTION; 
DELETE FROM movies
WHERE movie_id > 0; 

SELECT * FROM movies; 
-- 롤백 
ROLLBACK; 
SELECT * FROM movies;
```
### COMMIT
→ 메모리상에 일어난 변화를 영구적으로 저장
```mysql 
START TRANSACTION; 
INSERT INTO movies
(movie_title, price) 
VALUES ('아바타: 물의 길', 14000); 

SELECT * FROM movies; 
-- 커밋 
COMMIT; 
ROLLBACK; 
SELECT * FROM movies;
```
### SAVEPOINT
→ 롤백할 시점을 설정

```mysql
START TRANSACTION; 
INSERT INTO movies 
(movie_title, price) 
VALUES ('아바타: 물의 길', 14000); 

SAVEPOINT avatar; 

INSERT INTO movies 
(movie_title, price) 
VALUES ('앤트맨과 와스프: 퀀텀매니아', 14000); 

SELECT * FROM movies; 
ROLLBACK TO avatar; 

SELECT * FROM movies; 
COMMIT;
```

# Chap 7.  join
- 데이터베이스에서 기준이 되는 칼럼을 중심으로 서로 다른 테이블을 합쳐 원하는 결과를 도출하기 위해 테이블을 조합해주는 명령어
- 기준이 될 칼럼이 서로 다른 데이터베이스 테이블에 동일하게 존재해야 원하는 데이터를 도출할 수 있음.

### 내부 조인( INNER JOIN )
- 양쪽이 모두 값이 있는(NOT NULL) 반환
- ambiguous 오류 발생 가능

#### 서로 다른 테이블을 조인하기
```mysql
SELECT * FROM movies M 
JOIN reviews R 
ON M.movie_id = R.moive_id;
```
#### 여러 테이블을 조인하기
```
SELECT 
M.movie_id, m.movie_title, R.movie_grade, S.total_sales
FROM movies M
JOIN reviews R  
ON M.movie_id = R.movie_id
JOIN sales S
ON M.movie_id = S.movie_id;
```

#### 같은 테이블 내에서 조인하기
```mysql
SELECT 
S1.student_id, 
CONCAT_WS(' ', S1.first_name, S1.last_name) AS Student, S2.student_id, 
CONCAT_WS(' ', S2.first_name, S2.last_name) AS NextStudent 
FROM Student S1 
JOIN Student S2 
ON S1.student_id + 1 = S2.student_id; 
```

### 외부조인(OUTER JOIN)
-   JOIN 대상인 테이블의 데이터의 유무와 상관 없이 출력
-  LEFT or RIGHT 명령어로 조인한다.

```mysql
SELECT 
S1.student_id, 
CONCAT_WS(' ', S1.first_name, S1.last_name) AS Student, S2.student_id, 
CONCAT_WS(' ', S2.first_name, S2.last_name) AS NextStudent 
FROM Student S1 
LEFT JOIN Student S2 
ON S1.student_id + 1 = S2.student_id; 
ORDER BY S1.student_id
```
### 교차조인(CROSS JOIN)
- 조건 없이 모든 조합 반환 ( A * B )

``` mysql
SELECT 
	S1.first_name, S2.last_name 
FROM Student S1 
CROSS JOIN Student S2
ORDER BY S1.student_id
```


---
### 참고사이트
- 데이터베이스 개념 (오라클)
https://www.oracle.com/kr/database/what-is-database/
- 분산 데이터베이스(distributed databases) 종류
https://thechief.io/c/editorial/top-25-distributed-databases/
- 데이터 웨어 하우스에 대한 자세한 설명
https://www.guru99.com/data-warehousing.html
- 데이터 웨어하우스 Top 5
https://weld.app/blog/top-5-data-warehouses
- NoSQL 데이터베이스 랭킹
https://www.spiceworks.com/tech/artificial-intelligence/articles/what-is-nosql/
- 그래프 데이터베이스 서비스(neo4j)
https://neo4j.com/developer/graph-database/
- 그래프데이터베이스 종류
https://www.kdnuggets.com/2021/02/understanding-nosql-database-types-graph.html
- 클라우드 데이터베이스 종류
https://www.dbmaestro.com/blog/database-automation/top-7-cloud-databases
- 다중모델 데이터베이스 종류
https://www.predictiveanalyticstoday.com/top-multi-model-databases/
- 문서데이터베이스 종류
https://www.techtarget.com/whatis/definition/document-oriented-database
- json 데이터베이스 종류
https://www.mongodb.com/databases/json-database
- sql이란?
https://aws.amazon.com/ko/what-is/sql/
-  NoSql이란
https://aws.amazon.com/ko/nosql/
- 인덱스
https://mangkyu.tistory.com/96
- 정규화와 반정규화
https://sodayeong.tistory.com/106
