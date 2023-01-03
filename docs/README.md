```shell
mvn clean package docker:build -DskipTests -DpushImage
mvn clean package -DskipTests

cd docker
docker-compose up -d

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
```