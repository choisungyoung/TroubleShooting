## 에러
# 프라이빗 도커 레지스트리에 이미지 푸쉬시 아래 애러 발생
```
The push refers to repository [localhost:30500/jenkins-withdocker]
71d9689efc6e: Retrying in 1 second 
4cd0a6963662: Retrying in 1 second 
1252bfe806ec: Retrying in 1 second 
9b11310e8517: Retrying in 1 second 
c206f3314cf6: Retrying in 1 second 
c8e07207c3d5: Retrying in 5 seconds 
a0caf811b6c6: Waiting 
e95681debdfc: Waiting 
9c56ea9be22e: Waiting 
8cfd625ccf87: Waiting 
950f52971bcd: Waiting 
a7434b230280: Waiting 
2deaa2e46a73: Waiting 
67ecf08dcec5: Waiting 
2c3ea5378101: Waiting 
2b19fcdf5242: Waiting 
bad4af3237e8: Waiting 
fbcda7e88b91: Waiting 
3294d39bbfc4: Waiting 
7750c6b9c3b8: Waiting 
ca03ec048db4: Waiting 
5721f92f4170: Waiting 
596f2d04b897: Waiting 
691c1cd5e596: Waiting 
fb322da4726e: Waiting 
714a9e16c2f0: Waiting 
c8257f62a627: Waiting 
799760671c38: Waiting 
received unexpected HTTP status: 500 Internal Server Error
```


## 해결
# 도커 이미지 레지스트리 컨테이너 로그 확인

time="2022-02-14T06:45:46.211148795Z" level=error msg="response completed with error" err.code=unknown err.detail="`filesystem: mkdir /var/lib/registry/docker: permission denied`" err.message="unknown error" go.version=go1.11.2 http.request.host="localhost:30500" http.request.id=8c04e879-564b-4d56-b233-46e194625aad http.request.method=POST http.request.remoteaddr="10.44.0.0:46599" http.request.uri="/v2/jenkins-withdocker/blobs/uploads/" http.request.useragent="docker/20.10.12 go/go1.16.12 git-commit/459d0df kernel/5.13.0-28-generic os/linux arch/amd64 UpstreamClient(Docker-Client/20.10.12 \(linux\))" http.response.contenttype="application/json; charset=utf-8" http.response.duration=11.684664ms http.response.status=500 http.response.written=164 vars.name=jenkins-withdocker

# NFS에 마운트된 경로에 권한 부여

```
chmod 777 /<mountPath>/*
```

