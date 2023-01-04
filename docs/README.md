```shell
mvn clean package docker:build -DskipTests -DpushImage
mvn clean package -DskipTests

cd docker
docker-compose up -d
docker-compose down
docker-compose logs -f

cd lilishop-ui
cd buyer/
cnpm install
npm run build

cd manager/
cnpm install
npm run build

cd seller/
cnpm install
npm run build

cd xxl-job
docker build -t yiluxiangbei/xxl-job-admin:2.3.0 .
docker push yiluxiangbei/xxl-job-admin:2.3.0

docker-compose up xxl-job

mysql -h127.0.0.1 -uroot -p -P3301
lilishop
mysql -h127.0.0.1 -uroot -p -P3301 lilishop < init/mysql/lilishop.sql

yum install jq -y
curl -L -s 'https://registry.hub.docker.com/v2/repositories/library/hello-world/tags?page_size=1024' | jq '.results[]["name"]' | sed 's/\"//g' | sort -u
curl -L -s 'https://registry.hub.docker.com/v2/repositories/library/node/tags?page_size=1024' | jq '.results[]["name"]' | sed 's/\"//g' | sort -u
curl -L -s 'https://registry.hub.docker.com/v2/repositories/library/node/tags?page=2&page_size=1024' | jq '.results[]["name"]' | sed 's/\"//g' | sort -u
curl -L -s 'https://registry.hub.docker.com/v2/repositories/library/node/tags?page=3&page_size=1024' | jq '.results[]["name"]' | sed 's/\"//g' | sort -u

docker tag registry.cn-beijing.aliyuncs.com/luomor/admin:4.2.5.1 yiluxiangbei/lilishop-admin:4.2.5.1
docker push yiluxiangbei/lilishop-admin:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/consumer:4.2.5.1 yiluxiangbei/lilishop-consumer:4.2.5.1
docker push yiluxiangbei/lilishop-consumer:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/common-api:4.2.5.1 yiluxiangbei/lilishop-common-api:4.2.5.1
docker push yiluxiangbei/lilishop-common-api:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/seller-api:4.2.5.1 yiluxiangbei/lilishop-seller-api:4.2.5.1
docker push yiluxiangbei/lilishop-seller-api:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/manager-api:4.2.5.1 yiluxiangbei/lilishop-manager-api:4.2.5.1
docker push yiluxiangbei/lilishop-manager-api:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/buyer-api:4.2.5.1 yiluxiangbei/lilishop-buyer-api:4.2.5.1
docker push yiluxiangbei/lilishop-buyer-api:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/framework:4.2.5.1 yiluxiangbei/lilishop-framework:4.2.5.1
docker push yiluxiangbei/lilishop-framework:4.2.5.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/buyer-ui:4.2.4.1 yiluxiangbei/lilishop-buyer-ui:4.2.4.1
docker push yiluxiangbei/lilishop-buyer-ui:4.2.4.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/seller-ui:4.2.4.1 yiluxiangbei/lilishop-seller-ui:4.2.4.1
docker push yiluxiangbei/lilishop-seller-ui:4.2.4.1

docker tag registry.cn-beijing.aliyuncs.com/luomor/manager-ui:4.2.4.1 yiluxiangbei/lilishop-manager-ui:4.2.4.1
docker push yiluxiangbei/lilishop-manager-ui:4.2.4.1

docker rmi `docker images | grep none | awk '{print $3}'`
```

```
REPOSITORY                                                                                                       TAG                              IMAGE ID
    CREATED          SIZE
registry.cn-beijing.aliyuncs.com/luomor/admin                                                                    4.2.5.1                          4372ba69dc9d   10 minutes ago   677MB
registry.cn-beijing.aliyuncs.com/luomor/consumer                                                                 4.2.5.1                          45f12f9aecd8   10 minutes ago   836MB
registry.cn-beijing.aliyuncs.com/luomor/common-api                                                               4.2.5.1                          ca1de46dfd17   11 minutes ago   836MB
registry.cn-beijing.aliyuncs.com/luomor/seller-api                                                               4.2.5.1                          e4fa7f21a580   11 minutes ago   835MB
registry.cn-beijing.aliyuncs.com/luomor/manager-api                                                              4.2.5.1                          e86933b3a213   12 minutes ago   836MB
registry.cn-beijing.aliyuncs.com/luomor/buyer-api                                                                4.2.5.1                          567a09ff6c30   13 minutes ago   836MB
registry.cn-beijing.aliyuncs.com/luomor/framework                                                                4.2.5.1                          c24f4f1fb31b   14 minutes ago   645MB

REPOSITORY                                                                                                       TAG                              IMAGE ID
    CREATED          SIZE
registry.cn-beijing.aliyuncs.com/luomor/seller-ui                                                                4.2.4.1                          63592367b981   49 seconds ago   29.6MB
registry.cn-beijing.aliyuncs.com/luomor/manager-ui                                                               4.2.4.1                          54b44bbe4ddb   3 minutes ago    29.8MB
registry.cn-beijing.aliyuncs.com/lili-images/buyer-ui                                                            4.2.4.1                          0bc102eccb5c   5 minutes ago    26.8MB

docker-compose ps
     Name                   Command               State                                                  Ports
-------------------------------------------------------------------------------------------------------------------------------------------------------------
buyer            java -jar /buyer-api-4.2.5.jar   Up      0.0.0.0:8888->8888/tcp,:::8888->8888/tcp
buyer-ui         /docker-entrypoint.sh ngin ...   Up      0.0.0.0:8021->80/tcp,:::8021->80/tcp
common           java -jar /common-api-4.2. ...   Up      0.0.0.0:8890->8890/tcp,:::8890->8890/tcp
elasticsearch    /usr/local/bin/docker-entr ...   Up      0.0.0.0:9200->9200/tcp,:::9200->9200/tcp, 0.0.0.0:9300->9300/tcp,:::9300->9300/tcp
kibana           /usr/local/bin/kibana-docker     Up      0.0.0.0:5601->5601/tcp,:::5601->5601/tcp
lilishop-mongo   docker-entrypoint.sh mongod      Up      0.0.0.0:27011->27017/tcp,:::27011->27017/tcp
lilishop-mysql   docker-entrypoint.sh mysqld      Up      0.0.0.0:3301->3306/tcp,:::3301->3306/tcp, 33060/tcp
lilishop-redis   docker-entrypoint.sh redis ...   Up      0.0.0.0:6380->6379/tcp,:::6380->6379/tcp
logstash         /usr/local/bin/docker-entr ...   Up      0.0.0.0:4560->4560/tcp,:::4560->4560/tcp, 5044/tcp, 9600/tcp
manager          java -jar /manager-api-4.2 ...   Up      0.0.0.0:8887->8887/tcp,:::8887->8887/tcp
manager-ui       /docker-entrypoint.sh ngin ...   Up      0.0.0.0:8023->80/tcp,:::8023->80/tcp
rocket-broker    mqbroker -c /etc/rocketmq/ ...   Up      0.0.0.0:10909->10909/tcp,:::10909->10909/tcp, 0.0.0.0:10911->10911/tcp,:::10911->10911/tcp,
                                                          10912/tcp, 9876/tcp
rocket-console   sh -c java $JAVA_OPTS -jar ...   Up      0.0.0.0:8180->8180/tcp,:::8180->8180/tcp
rocket-server    /bin/sh -c cd ${ROCKETMQ_H ...   Up      10909/tcp, 10911/tcp, 10912/tcp, 0.0.0.0:9876->9876/tcp,:::9876->9876/tcp
seller           java -jar /seller-api-4.2. ...   Up      0.0.0.0:8889->8889/tcp,:::8889->8889/tcp
seller-ui        /docker-entrypoint.sh ngin ...   Up      0.0.0.0:8022->80/tcp,:::8022->80/tcp
xxl-job          sh -c java -jar $JAVA_OPTS ...   Up      0.0.0.0:9003->9001/tcp,:::9003->9001/tcp
```