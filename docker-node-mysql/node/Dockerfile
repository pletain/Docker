# node 컨테이너 기반
FROM node


# 작업디렉토리를 생성하고 현 소스파일들을 전체를 붙여 넣는다.
WORKDIR /src
ADD . /src # node 파일 안에 있는 
# models,app.js,.env 등등 모든 소스를 위의 소스 디렉토리로 가져다 준다.

# src 폴더로 이동한 다음에 패키지를 install 한다
RUN cd /src && npm install

# Expose port
EXPOSE  3000 #외부 포트를 3000번을 실행함

# Run app
CMD ["node", "/src/app.js"] #시작 지점이 app.js임
RUN apt-get update && apt-get install -y netcat

# Shell scritp에서 지속적으로 포트를 체크한 후 nodejs를 실행
RUN chmod +x docker-entrypoint.sh  
ENTRYPOINT ./docker-entrypoint.sh

# entrypoint는 인자를 받을 수 있고, cmd는 받을 수 없다.