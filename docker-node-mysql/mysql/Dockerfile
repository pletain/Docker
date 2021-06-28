# node 컨테이너 기반
FROM mysql

# 환경변수
ENV MYSQL_ROOT_PASSWORD example # DB 비밀번호
ENV MYSQL_DATABASE company  #데이터베이스명

# sql-scripts의 CreateTable.sql,InsertData.sql을
# 실행 되는 위치에 가져다 놓기 위해 COPY해 줘야 한다.
COPY ./sql-scripts/ /docker-entrypoint-initdb.d/

# Run app
CMD ["--default-authentication-plugin=mysql_native_password"]