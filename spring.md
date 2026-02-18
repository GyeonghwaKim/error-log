
---

### 1. Spring Batch 다중 Job 에러

**🚨 에러 로그**
`java.lang.IllegalStateException: Job name must be specified in case of multiple jobs`

**🔍 원인**
Spring Batch에 여러 개의 Job이 등록되어 있으나, 어떤 Job을 실행할지 명시되지 않음.

**💡 해결**
설정 파일에 실행할 Job 이름을 정확히 지정하거나, 앱 실행 시 인자로 전달한다.

* **방법 1 (CLI 파라미터 전달):** `./gradlew bootRun --args="--spring.batch.job.name=simpleJob"`
* **방법 2 (설정 파일 명시):** `spring.batch.job.name: simpleJob`

---

### 2. JPA JPQL 엔티티 인식 에러

**🚨 에러 로그**
`org.hibernate.query.sqm.UnknownEntityException: Could not resolve root entity 'orders'`

**🔍 원인**
JPQL 쿼리 작성 시 자바 엔티티 클래스 이름이 아닌, DB 테이블 이름(`orders`)을 사용하여 엔티티를 찾지 못함. (JPQL은 대소문자 구분이 엄격함)

**💡 해결**
테이블명 대신 **자바 엔티티 클래스명**으로 쿼리를 수정한다.

* **❌ AS-IS (에러):** `SELECT o FROM orders o`
* **✅ TO-BE (해결):** `SELECT o FROM Order o`

---
