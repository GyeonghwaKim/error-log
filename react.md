

---

## 📋 React 환경 변수 접두사 규칙 에러 정리

* **원인**: React(CRA) 빌드 시스템은 보안을 위해 특정 접두사가 붙지 않은 변수를 브라우저로 전달하지 않고 차단함
* **현상**: `.env` 파일에 변수를 정의했음에도 `process.env.변수명` 호출 시 `undefined` 반환
* **해결 방법**: 모든 변수명 앞에 **`REACT_APP_`** 접두사를 필수적으로 추가
* 잘못된 예: `BASE_URL=https://api.com`
* 올바른 예: **`REACT_APP_`**`BASE_URL=https://api.com`


* **호출 코드**: `process.env.REACT_APP_BASE_URL`
* **주의 사항**: 변수명을 수정한 후에는 반드시 개발 서버를 **재시작(Restart)**해야 반영됨

---
## 📋 React 개발 에러 로그

에러 내용: Invalid DOM property for. Did you mean htmlFor?

발생 위치: <label> 태그의 for 속성 사용 시 발생

원인: JSX는 JavaScript 기반이므로 예약어인 for 대신 htmlFor를 사용해야 함

해결 방법: for="id"를 htmlFor="id"로 수정

---
## 📋 React 개발 에러 로그

오류 상황: 배열의 마지막 요소에 접근하기 위해 array[-1] 사용

현상: 에러는 나지 않으나 undefined 반환 (JavaScript는 음수 인덱스 브라우징 미지원)

해결 방법:

최신 방식: array.at(-1) 사용 (가장 권장)

전통적 방식: array[array.length - 1] 사용
