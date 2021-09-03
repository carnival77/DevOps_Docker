# DevOps_Docker

# Project Instruction
Implemented Web Poll service employing Docker in Epitech.

The application you are working on during this project is a simple poll web application. Poll is a Python Flask
web application that gathers the votes to push them into a Redis queue. The Java Worker consumes the
votes stored in the Redis queue, then pushes it into a PostgreSQL database. Finally, the Node.js Result web
application fetches the votes from the DB and displays the result.


# 다중 컨테이너와 Docker 활용을 통한 MSA DevOps 구현
## 2. 프로젝트 개요
### A.	Monolithic한 어플리케이션을 Microservice로 분리
#### i.	소스코드에서 하나의 Monolithic한 어플리케이션의 서비스단, 비즈니스 로직, 데이터 엑세스 부분을, 즉, 프론트엔드, 백엔드, DB 등의 마이크로서비스들로 나눠 각기 다른 컨테이너에 놓는다.
### B.	도커 활용해 각 Microservice의 컨테이너화
#### i.	도커 파일로 빌드하여 이미지로 만들어 컨테이너화한 다음, docker compose 단일 명령을 사용하여 모두 실행하여, 하나의 어플리케이션을 실행한다.
## 3. 프로젝트 구조
![DevOps_structure](https://user-images.githubusercontent.com/52997401/86203711-9fe57d00-bba0-11ea-99a5-8e1a9546814f.png)
## 4.	프로젝트 프로세스
### A.	활용 기능 : 
#### i.	Python과 Node JS로 작성된 poll, result 프론트 엔드 소스 코드
#### ii.	Redis 와 PostgreSQL을 활용한 데이터 전송 및 저장 기능
#### iii.	Java로 작성된 worker 백엔드 소스코드
### B.	구체적 프로세스
#### i.	Docker compose 후, http://localhost:5000  로 접속하면, poll 투표 화면이 보인다.
#### ii.	투표를 하면, 투표 데이터가 캐시로 Redis에 저장된다.
#### iii.	Worker 백엔드는 이것을 Postgres DB에 vote 데이터테이블을 만든 후 저장한다. 
#### iv.	http://localhost:5001 로 redirect 되어 투표가 집계된 후의 result 결과 화면이 보인다.

### C. 결과 화면
#### i. 투표 화면 ( http://localhost:5000 ) 
##### 1. 선택 전
![image](https://user-images.githubusercontent.com/52997401/131967179-187e2b32-f3cf-432e-9227-a4d7e08c1984.png)
##### 2. 선택 후
![image](https://user-images.githubusercontent.com/52997401/131967291-392229a6-6756-4da6-897c-3d84389c914a.png)
#### ii. 결과 화면 ( http://localhost:5001 )
![DevOps_result](https://user-images.githubusercontent.com/52997401/86203389-d79ff500-bb9f-11ea-8962-a5c42e433790.png)

