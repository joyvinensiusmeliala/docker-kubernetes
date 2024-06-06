# Docker dan Kubernetes: Pengantar Singkat

Docker dan Kubernetes adalah dua teknologi yang sangat populer dalam dunia pengembangan dan pengelolaan aplikasi berbasis container. Mereka sering digunakan bersama-sama, tetapi masing-masing memiliki fungsi dan tujuan yang berbeda. Berikut adalah penjelasan tentang Docker dan Kubernetes:

## Pengenalan Docker

### Apa itu Docker?
Docker adalah platform open-source yang memungkinkan pengembang untuk membangun, mengemas, dan menjalankan aplikasi di dalam container. Container adalah unit komputasi yang ringan dan portabel yang mencakup aplikasi dan semua dependensinya sehingga aplikasi bisa berjalan dengan konsisten di berbagai lingkungan.

## Mengapa Docker?
### Manfaat Docker:
1. **Portabilitas**: Aplikasi yang dikemas dalam container dapat berjalan di mana saja, baik di laptop pengembang, server fisik, mesin virtual, data center, atau cloud.
2. **Konsistensi**: Menghilangkan masalah "it works on my machine" dengan memastikan lingkungan aplikasi yang konsisten di berbagai tahap pengembangan, pengujian, dan produksi.
3. **Efisiensi Sumber Daya**: Container berbagi kernel host, membuat mereka lebih ringan dan cepat dibandingkan dengan mesin virtual (VM).
4. **Penskalaan Mudah**: Memungkinkan penskalaan aplikasi dengan mudah dengan menjalankan beberapa container dari image yang sama.

## Komponen Utama Docker
### 1. Docker Engine
Docker Engine adalah aplikasi client-server yang terdiri dari beberapa komponen utama:
- **Daemon Docker (dockerd)**: Proses server yang mengelola objek Docker (image, container, network, dan volume) dan menangani permintaan dari API Docker.
- **API REST**: Antarmuka yang memungkinkan program untuk berinteraksi dengan daemon Docker.
- **Docker CLI**: Alat command-line yang memungkinkan pengguna untuk berinteraksi dengan Docker menggunakan command seperti `docker run`, `docker build`, `docker pull`, dll.

### 2. Docker Images
Docker image adalah template read-only yang digunakan untuk membuat container. Image ini bisa diibaratkan sebagai snapshot dari aplikasi yang berisi sistem file, dependensi, dan konfigurasi aplikasi.

### 3. Docker Containers
Container adalah instance yang berjalan dari Docker image. Mereka mengemas aplikasi dan semua dependensinya ke dalam satu unit yang bisa dijalankan di mana saja.

### 4. Docker Hub
Docker Hub adalah registry online yang memungkinkan Anda untuk menyimpan dan mendistribusikan Docker images. Pengguna bisa menarik image dari Docker Hub untuk membuat container atau mendorong image yang mereka buat ke Docker Hub untuk berbagi dengan orang lain.

### 5. Docker Compose
Docker Compose adalah alat untuk mendefinisikan dan menjalankan aplikasi multi-container. Dengan menggunakan file `docker-compose.yml`, Anda bisa mengonfigurasi layanan aplikasi, jaringan, dan volume.

## Cara Kerja Docker
1. **Build**: Pengembang membuat Dockerfile yang mendefinisikan lingkungan aplikasi dan cara membangunnya. Dockerfile ini digunakan untuk membangun Docker image.
2. **Ship**: Docker image didistribusikan ke registry seperti Docker Hub.
3. **Run**: Docker image ditarik dari registry dan digunakan untuk membuat dan menjalankan container di berbagai lingkungan.

## Konsep Dasar Docker

### Dockerfile
Dockerfile adalah file teks yang berisi serangkaian instruksi untuk membangun Docker image. Berikut adalah contoh sederhana dari Dockerfile:

```dockerfile
# Gunakan image dasar
FROM ubuntu:20.04

# Install dependencies
RUN apt-get update && apt-get install -y python3 python3-pip

# Salin aplikasi ke dalam image
COPY . /app

# Set working directory
WORKDIR /app

# Install dependencies aplikasi
RUN pip3 install -r requirements.txt

# Tentukan perintah yang akan dijalankan ketika container dimulai
CMD ["python3", "app.py"]
