# Kafka_study2
IntelliJ로 Docker에 Kafka설치하고 Spring Boot에서 Kafka사용하기

## Docker에 Kafka설치
+ YAML파일이 필요하다
  + docker-compose.yaml
  + YAML파일은 블럭구조를 가지므로 들여쓰기를 주의해서 작성해야한다
+ 2개의 이미지가 필요하다
  + kafka
  + zookeeper : 카프카 코디네이터

### 설치 명령
YAML파일이 있는 디렉토리 위치에서 명령을 실행해야한다


**docker-compose up -d**
+ 설치 확인1 : docker ps
+ 설치 확인2 : docker desktop에서 확인


![image](https://github.com/user-attachments/assets/f42dae31-77fb-442f-9473-e26973a66511)
