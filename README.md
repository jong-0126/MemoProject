📌 Memo API

📖 개요

Memo API는 메모를 생성, 조회, 수정 및 삭제할 수 있는 RESTful API입니다. 모든 데이터는 JSON 형식으로 주고받으며, 각각의 메모는 다음과 같이 구성됩니다:

식별자 (id)

제목 (title)

내용 (contents)

📌 API 명세

1️⃣ 메모 생성 (CREATE)

URL: POST /memos

Request Body:

{
  "title": "메모 제목",
  "contents": "메모 내용"
}

Response:

{
  "id": 1,
  "title": "메모 제목",
  "contents": "메모 내용"
}

2️⃣ 메모 전체 목록 조회 (READ)

URL: GET /memos

Response:

[
  {
    "id": 1,
    "title": "첫 번째 메모",
    "contents": "내용입니다."
  },
  {
    "id": 2,
    "title": "두 번째 메모",
    "contents": "또 다른 내용입니다."
  }
]

데이터가 없는 경우:

[]

3️⃣ 특정 메모 조회 (READ)

URL: GET /memos/{id}

Response:

{
  "id": 1,
  "title": "첫 번째 메모",
  "contents": "내용입니다."
}

4️⃣ 메모 전체 수정 (UPDATE - PUT)

URL: PUT /memos/{id}

Request Body:

{
  "title": "수정된 제목",
  "contents": "수정된 내용"
}

Response:

{
  "id": 1,
  "title": "수정된 제목",
  "contents": "수정된 내용"
}

5️⃣ 메모 제목 일부 수정 (UPDATE - PATCH)

URL: PATCH /memos/{id}/title

Request Body:

{
  "title": "변경된 제목"
}

Response:

{
  "id": 1,
  "title": "변경된 제목",
  "contents": "기존 내용 유지"
}

6️⃣ 메모 삭제 (DELETE)

URL: DELETE /memos/{id}

Response:

{
  "message": "삭제 완료"
}

⚠️ 오류 처리

✔ 존재하지 않는 메모 ID 요청 시 적절한 예외 처리를 통해 오류 메시지 반환
✔ 필수 데이터가 누락된 요청에 대해 유효성 검사 수행

🛠 기술 스택

언어: Java

프레임워크: Spring Boot

데이터베이스: H2 (또는 MySQL, PostgreSQL 등 확장 가능)

빌드 도구: Gradle/Maven

통신 형식: JSON (REST API)

🚀 실행 방법

1️⃣ 프로젝트 클론:

git clone https://github.com/your-repository/memo-api.git

2️⃣ 의존성 설치:

./gradlew build

3️⃣ 프로젝트 실행:

./gradlew bootRun

4️⃣ API 테스트: Postman 또는 cURL을 사용하여 API 호출

📌 추가 사항

✅ JWT 인증 추가 가능
✅ Swagger UI 문서화 가능
✅ Redis 캐싱 적용 가능

