# 오픈소스소프트웨어실습 - FastAPI

이 프로젝트는 FastAPI를 사용하여 간단한 REST API 서버를 구축하고, JSON 파일(`courses.json`)을 활용하여 수강 기록 데이터를 읽고 수정하는 실습 과제입니다.

## 개발자 정보
- **학번**: 2021204045
- **이름**: 이성민


## 주요 기능
- **GET /courses**: `courses.json` 파일에 저장된 모든 수강 기록 리스트를 반환합니다.
- **POST /courses**: 새로운 수강 과목 정보를 받아 기존 JSON 리스트에 추가하고 파일에 저장합니다.
- **데이터 영속성**: 모든 데이터는 메모리가 아닌 로컬 JSON 파일에 저장되어 서버 재시작 후에도 유지됩니다.
- **오류 처리**: Pydantic 모델을 사용하여 잘못된 데이터 형식이 들어와도 서버가 종료되지 않고 적절한 에러 응답을 보냅니다.

## 실행 방법

### 1. 필수 라이브러리 설치
프로젝트 실행을 위해 필요한 패키지(`fastapi`, `uvicorn`)를 설치합니다.
```bash
pip install -r requirements.txt
```
### 2. 서버 실행
프로젝트 루트 디렉토리에서 아래 명령어를 입력하여 FastAPI 서버를 실행합니다.

```bash
uvicorn main:app --reload
```
서버가 실행되면 http://127.0.0.1:8000/courses 주소로 접근이 가능합니다.

### 3. 프로젝트 구조
- **main.py**: FastAPI 서버 로직 및 API 엔드포인트 구현
- **courses.json**: 수강 기록 데이터가 저장되는 JSON 파일
- **requirements.txt**: 프로젝트 의존성 라이브러리 목록
- **README.md**: 프로젝트 설명 문서

### 4. API 테스트 (Postman)
- **GET /courses**: 전체 데이터 조회
- **POST /courses**: 새 데이터 추가
#### Body (JSON):

```json
{
    "course_name": "오픈소스소프트웨어실습",
    "year": "2026",
    "semester": "1",
    "grade": "A+" 
}
```
