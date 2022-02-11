## 에러
# 프라이빗 도커 레지스트리에 이미지 푸쉬시 아래 애러 발생
The push refers to repository [<IP>30500/jenkins-withdocker]
Get "https://master1.example.com:30500/v2/": http: server gave HTTP response to HTTPS client


## 해결
# /etc/docker/daemon.json 파일에 아래 추가

```
{

    "insecure-registries": ["<IP>:5000"]

}
```
