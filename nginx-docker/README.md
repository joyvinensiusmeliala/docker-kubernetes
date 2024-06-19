# Deploy Web HTML with Dockerfile

## Buat Dockerfile terlebih dahulu 

1. Docker Build

-  Buat Docker Images untuk file HTML yang ingin anda deploy

```sh
docker build -t website-free .
```

2. Docker Build Container 

-  Buat Docker Container untuk file HTML yang ingin anda deploy

```sh
docker build -t website-free .
```

3. Docker Run Container 

-  Buat Docker Images untuk file HTML yang ingin anda deploy

```sh
docker container create --name website-free -p 8081:80 website-free:1.0
```