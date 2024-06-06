# Menjalankan NGINX menggunakan Docker Compose

Berikut adalah langkah-langkah untuk menjalankan Nagios XI dalam container Docker menggunakan Docker Compose.

## Langkah 1: Menyiapkan Docker Compose

1. Buat file `docker-compose-nginx.yml`:

    ```bash
    touch docker-nginx-compose.yml
    ```

2. Edit file `docker-compose-nginx.yml` dengan konten berikut:

    ```yaml
    version: '3.8'
    
    services:
      nginx_container1:
        image: nginx:latest
        container_name: nginx_container1
        ports:
          - "8080:80"  # Port mapping, menjembatani port 8080 host ke port 80 container
        restart: always  # Restart otomatis saat kontainer berhenti

      nginx_container2:
        image: nginx:latest
        container_name: nginx_container2
        ports:
          - "8081:80"  # Port mapping, menjembatani port 8081 host ke port 80 container
        restart: always  # Restart otomatis saat kontainer berhenti
    ```

## Langkah 2: Menjalankan Docker Compose

Jalankan Docker Compose dengan file yang sudah dibuat:

```bash
sudo docker-compose -f docker-compose-nginx.yml up -d
```

## Langkah 3: Memeriksa Status dan Mengakses Nagios XI

1. Memeriksa status kontainer:

```bash
sudo docker-compose -f docker-compose-nginx.yml ps
```

2. Melihat log dari kontainer:

```bash
sudo docker-compose -f docker-compose-nginx.yml logs   
```

3. Mengakses Nginx XI:
Buka browser web dan akses Nginx menggunakan IP publik atau hostname dari server Anda pada port 8080 dan 8081. Sebagai contoh:

```bash
http://<your_server_ip>:8080
```
