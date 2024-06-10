# Belajar Docker

## Create and Pull Docker Images

1. Docker pull

-  Mengunduh image dari Docker Hub atau registry lain.

```sh
docker pull IMAGE
```

![Deskripsi Gambar](images/docker-nginx-1-alpine-slim.png)

2. Docker images

-  Menampilkan daftar image yang ada di sistem lokal.

```sh
docker images
```

![Deskripsi Gambar](images/docker-images.png)

3. Docker images

-  Menampilkan daftar container yang sedang running di sistem lokal.

```sh
docker container ls
```

-  Menampilkan daftar container yang sedang running dan tidak running di sistem lokal.

```sh
docker container ls --all
```

4. Docker container create

-  Membuat container dari images yang sudah ada di server

```sh
docker container create --name nginxjoy01 nginx:1-alpine-slim
```

5. Docker container run

-  Menjalankan container dari images yang sudah ada di server

```sh
docker container start nginxjoy01
```

6. Docker container rm dan stop

-  Menghapus container yang sudah ada di server

```sh
docker container rm nginxjoy01
```

note : sebelum menghapus container, anda harus memastikan container yang ingin di hapus harus dalam keadaan berhenti 

```sh
docker container stop nginxjoy01
```

## Membuka Port untuk Container

7. Docker container create

-  Membuat container dari images Nginx di latar belakang pada port 80 yang sudah ada di server 

```sh
docker container create --name nginxjoy01 -p 8083:80 nginx:1-alpine-slim
```

8. Running container yang sudah di buat 

```sh
docker container start nginxjoy01 nginxjoy02
```

## Menghapus images 

9. Docker rmi

-  Menghapus image dari sistem lokal.

```sh
docker images rm IMAGE
```

## Membuat Docker Images menggunakan Dockerfile

10. Docker build

-   Membuat Docker Images menggunakan Dockerfile
-   note : sebelum running file di atas anda terlebih dahulu harus membuat Dockerfile

```sh
docker build --tag app-golang:1.0 .
```

11. Docker container create

-  Membuat container dari images Nginx di latar belakang pada port 8080 yang sudah ada di server 

```sh
docker container create --name app1 -p 8085:8080 app-golang1.0
```

12. Running container yang sudah di buat 

```sh
docker container start app1 
```

Itu adalah beberapa perintah dasar yang dapat digunakan untuk bekerja dengan Docker. Tentu saja, Docker memiliki banyak perintah lain yang lebih spesifik untuk kebutuhan yang lebih lanjut. Anda dapat memeriksa dokumentasi Docker untuk informasi lebih lengkap dan mendetail.