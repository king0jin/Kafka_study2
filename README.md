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


![image](https://github.com/user-attachments/assets/50954bab-05bc-48e8-ad1a-033a7928d5dd)


![image](https://github.com/user-attachments/assets/dbe66515-7197-4a62-9154-d299695d964b)


+ 설치 확인1 : docker ps
+ 설치 확인2 : docker desktop에서 확인


![image](https://github.com/user-attachments/assets/e7477323-7465-4994-966a-a58d51e1cf8a)


![image](https://github.com/user-attachments/assets/4f29aadc-b4e2-45fa-9b26-de6b03257abc)


### Kafka Test
#### Topic 생성하여 메세지 전송
1. kafka컨테이너로 접속 : docker exec -it kafka /bin/bash
2. 실행 관련 명령들이 저장되어 있는 bin디렉토리로 이동 : cd /opt/kafka/bin
3. Topic 생성 : kafka-console-producer.sh --topic exam-topic1117 --broker-list localhost:9092
   + 메세지 입력


![image](https://github.com/user-attachments/assets/b7a79657-b849-4fe4-a102-1ab7fd038564)


#### 전송한 메세지 확인
새로운 터미널을 새로 열어서 실행한다
+ kafka-console-consumer.sh --topic exam-topic1117 --bootstrap-server localhost:9092 --from-beginning


입력한 메세지가 전송되어서 보인다 


![image](https://github.com/user-attachments/assets/6940affa-3e73-4d08-99b0-96c325e6aa5f)
---
## Spring Boot에서 Kafka사용 
**먼저, java application Runtime과 Development Kit확인을 해야한다**
+ java -version
+ javac -version
+ Spring Framework IDE 설치 : IntelliJ
  + Spring Boot Project 생성
  + 의존성 추가 : 
