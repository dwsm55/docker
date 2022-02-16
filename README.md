# docker
node를 이용한 docker 샘플

# docker 빌드
docker build -f Dockerfile -t node-docker .

# 이미지 확인
docker images 
<table>
    <tr>
        <td>node-docker</td>
        <td>latest</td>		
        <td>1f07c40e68f8</td>
        <td>8 minutes ago</td>          	
        <td>121MB</td>
    </tr>		
</table>

# docker 백그라운드 실행
docker run -d -p 8080:8080 node-docker

# docker 실행 확인
docker ps<br>

<table>
    <tr style="background-color:lightgrey">
        <th>CONTAINER ID</th>
        <th>IMAGE</th>		
        <th>COMMAND</th>
        <th>CREATED</th>
        <th>STATUS</th>
        <th>PORTS</th>
        <th>NAMES</th>
    </tr>
    <tr>
        <td>e0b86e45ee21</td>
        <td>node-docker</td>		
        <td>"node index.js"</td>
        <td>2 minutes ago</td>          	
        <td>Up 23 seconds</td>
        <td>0.0.0.0:8080->8080/tcp, :::8080->8080/tcp</td>
        <td>sleepy_zhukovsky</td>
    </tr>		
</table>

# 동작 확인
http://127.0.0.1:8080/

# docker 실행 중지
docker stop <b>sleepy_zhukovsky</b>

# docker 이미지 삭제 
docker rmi -f  <이미지이름>

# tag
docker tag node-docker:latest <도커계정>/docker:v1

# docker push
docker push <도커계정>/docker:tagname