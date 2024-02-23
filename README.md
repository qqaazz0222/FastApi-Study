# FastAPI 공부

![FastAPI](readmeAssets/Untitled.png)

<aside>
🔗 [공식 홈페이지](https://fastapi.tiangolo.com/ko/)<br/>
🔗 [공식 문서](https://fastapi.tiangolo.com)<br/>
🔗 [소스 코드](https://github.com/tiangolo/fastapi)
</aside>
<br/>
> FastAPI는 현대적이고, 빠르며(고성능), 파이썬 표준 타입 힌트에 기초한 Python3.8+의 API를 빌드하기 위한 웹 프레임워크입니다.

# Fast API의 주요 특징

-   **빠름** : NodeJS 및 GO와 대등할 정도로 매우 높은 성능. **사용 가능한 가장 빠른 파이썬 프레임워크 중 하나.**
-   **빠른 코드 작성** : 약 200%에서 300%까지 기능 개발 속도 증가
-   **적은 버그** : 개발자에 의한 에러 약 40% 감소
-   **직관적** : 훌륭한 편집기 지원. 모든 곳에서 자동 완성. 적은 디버깅 시간.
-   **쉬움** : 쉽게 사용하고 배우도록 설계. 적은 문서 읽기 시간
-   **짧음** : 코드 중복 최소화. 각 매개변수 선언의 여러 기능. 적은 버그
-   **견고함**
-   **표준 기반** : API에 대한 개방형 표준 기반

# FastAPI 사용해보기

## 1. 설치

<aside>
💡 Python 3.6 이상에서 시용

</aside>

### 1-1. fastapi

-   FastAPI는 Python 기반 웹 프레임워크로, 최근 인기가 높아지고 있는 프레임워크
-   비동기 처리 지원 및 빠른 속도와 현대적인 기능 제공
-   Swagger와 같은 API 문서 자동화 기능 지원
-   Pydantic과 함께 사용하여 데이터 유효성 검사 가능

```
$ pip install fastapi
```

### 1-2. uvicorn

-   ASGI(Asynchronous Server Gateway Interface) 서버
-   비동기 처리를 지원하여, 높은 성능을 발휘
-   다양한 웹 프레임워크와 함께 사용 가능

<aside>
💡 FastAPI를 ASGI 서버인 Uvicorn의 비동기 처리와 함께 활용하여, 멀티스레드 방식의 기존 웹 어플리케이션보다 더욱 빠르고 안정적인 어플리케이션 개발 가능

</aside>

```
$ pip install uvicorn
```

# 2. 파일 생성

-   **server.py**

```python
from typing import Optional
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"msg": "Server Is Working"}
```

# 3. 서버 실행

```
// 명령어 : uvicorn [파일이름]:app --reload --host=0.0.0.0 --port=[포트 번호]
$ uvicorn server:app --reload --host=0.0.0.0 --port=5050
```

# 4. 테스트

-   GET /

![Untitled](readmeAssets/Untitled%201.png)

# 5. API 문서 보기

## 5-1. Swagger UI API 문서 보기

-   GET /docs (http://localhost:5050/docs)

![Untitled](readmeAssets/Untitled%202.png)

## 5-2. ReDoc API 문서 보기

-   GET /redoc (http://localhost:5050/redoc)

![Untitled](readmeAssets/Untitled%203.png)

# 6. 파일 구조

<aside>
🔗 [tiangolo/full-stack-fastapi-postgresql](https://github.com/tiangolo/full-stack-fastapi-postgresql/tree/master/src/backend/app/app)
</aside><br/>

<aside>
root<br/>
┠ api<br/>
┠ core<br/>
┠ crud<br/>
┠ db<br/>
┠ models<br/>
┠ schemas<br/>
┠ **init**.py<br/>
┠ server.py<br/>
┖ tests<br/>
</aside>
