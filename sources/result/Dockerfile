# 공식 node 런타임을 상위 이미지로 사용
FROM node:10

# 작업 디렉토리를 /usr/src/app으로 설정
WORKDIR /usr/src/app

# 앱 의존성 설치
# 가능한 경우(npm@5+) package.json과 package-lock.json을 모두 복사하기 위해
# 와일드카드를 사용
# 작업 디렉토리로 모든 내용 복사
COPY package*.json ./

RUN npm install
# 프로덕션을 위한 코드를 빌드하는 경우
# RUN npm ci --only=production

# 앱 소스 추가
COPY . .

# 이 컨테이너 외부에서 포트 80을 사용할 수 있도록 합니다.
EXPOSE 80

# 앱 실행을 위한 명령어
CMD [ "node", "server.js" ]
