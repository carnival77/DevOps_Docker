# 공식 python 런타임을 상위 이미지로 사용
FROM python:3.7-alpine

# 작업 디렉토리를 /usr/src/app으로 설정
WORKDIR /usr/src/app

# 환경변수 정의
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0

# requirements.txt 추가
ADD requirements.txt /usr/src/app/requirements.txt
COPY requirements.txt requirements.txt

# requirements.txt에 지정된 필요한 패키지를 설치합니다.
RUN pip install -r requirements.txt

# 설치된 내용 작업 디렉토리에 추가
COPY . .
ADD . /usr/src/app

# 이 컨테이너 외부에서 포트 80을 사용할 수 있도록 합니다.
EXPOSE 80

# 앱 실행을 위한 명령어
CMD ["python","app.py"]