# Menjalankan Nagios XI menggunakan Docker Compose

Berikut adalah langkah-langkah untuk menjalankan Nagios XI dalam container Docker menggunakan Docker Compose.

## Langkah 1: Menyiapkan Docker Compose

1. Buat file `docker-compose-nagios.yml`:

    ```bash
    touch docker-nagios-compose.yml
    ```

2. Edit file `docker-compose-nagios.yml` dengan konten berikut:

    ```yaml
    version: '3.8'

    services:
      nagiosxi:
        image: joyvinensius/nagiosxi:latest
        container_name: nagiosxi
        ports:
          - "8082:80"  # Port mapping host ke container (8082 host ke 80 container)
        environment:
          - TZ=Asia/Jakarta  # Ganti dengan zona waktu yang sesuai
        restart: always
    ```

## Langkah 2: Menjalankan Docker Compose

Jalankan Docker Compose dengan file yang sudah dibuat:

```bash
sudo docker-compose -f docker-compose-nagios.yml up -d
```

## Langkah 3: Memeriksa Status dan Mengakses Nagios XI

1. Memeriksa status kontainer:

```bash
sudo docker-compose -f docker-nagios-compose.yml ps
```

2. Melihat log dari kontainer:

```bash
sudo docker-compose -f docker-nagios-compose.yml logs   
```

3. Mengakses Nagios XI:
Buka browser web dan akses Nagios XI menggunakan IP publik atau hostname dari server Anda pada port 8080. Sebagai contoh:

```bash
http://<your_server_ip>:8080
```


