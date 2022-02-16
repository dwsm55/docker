# docker
node를 이용한 docker 샘플

# docker 빌드
docker build -f Dockerfile -t node-docker .

# 이미지 확인
docker images 
====================================
node-docker                                     latest         1f07c40e68f8   8 minutes ago   121MB<br>

# docker 백그라운드 실행
docker run -d -p 8080:8080 node-docker

# docker 실행 확인
docker ps
====================================
CONTAINER ID   IMAGE         COMMAND           CREATED         STATUS          PORTS                                       NAMES<br>
e0b86e45ee21   node-docker   "node index.js"   2 minutes ago   Up 23 seconds   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp   sleepy_zhukovsky

# 동작 확인
http://127.0.0.1:8080/

# docker 실행 중지
docker stop sleepy_zhukovsky

# docker 이미지 삭제 
docker rmi -f  <이름>
