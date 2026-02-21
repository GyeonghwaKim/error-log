

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
