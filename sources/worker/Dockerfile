# 공식 maven 런타임을 상위 이미지로 사용
FROM maven:3.5-jdk-8-alpine AS builder

# 작업 디렉토리를 /usr/src/app으로 설정
COPY . /usr/src/app
WORKDIR /usr/src/app

# 앱 의존성 설치
RUN mvn dependency:resolve
RUN mvn package

# 앱 실행을 위한 명령어
FROM openjdk:8-jre-alpine
COPY --from=builder /usr/src/app/target/worker-jar-with-dependencies.jar .
CMD java -jar worker-jar-with-dependencies.jar