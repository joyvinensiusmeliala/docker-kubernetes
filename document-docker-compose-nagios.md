# Menjalankan Nagios XI menggunakan Docker Compose

Berikut adalah langkah-langkah untuk menjalankan Nagios XI dalam container Docker menggunakan Docker Compose.

## Langkah 1: Menyiapkan Docker Compose

1. Buat file `docker-nagios-compose.yml`:

    ```bash
    touch docker-nagios-compose.yml
    ```

2. Edit file `docker-nagios-compose.yml` dengan konten berikut:

    ```yaml
    version: '3.8'

    services:
      nagiosxi:
        image: joyvinensius/nagiosxi:latest
        container_name: nagiosxi
        ports:
          - "8080:80"  # Port mapping host ke container (8080 host ke 80 container)
        environment:
          - TZ=Asia/Jakarta  # Ganti dengan zona waktu yang sesuai
        restart: always
    ```

## Langkah 2: Menjalankan Docker Compose

Jalankan Docker Compose dengan file yang sudah dibuat:

```bash
sudo docker-compose -f docker-nagios-compose.yml up -d
```

## Langkah 2: Menjalankan Docker Compose

Jalankan Docker Compose dengan file yang sudah dibuat:

```bash
sudo docker-compose -f docker-nagios-compose.yml up -d
```

