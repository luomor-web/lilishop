```shell
mvn clean package docker:build -DskipTests -DpushImage
mvn clean package -DskipTests

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
```