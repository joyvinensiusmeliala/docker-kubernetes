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

## Kubernetes

Kubernetes adalah platform open-source untuk otomatisasi penyebaran, penskalaan, dan pengelolaan aplikasi container. Kubernetes sering disebut sebagai "K8s" dan merupakan standar de facto untuk orkestrasi container.

### Fitur Utama Kubernetes:

- **Pods**: Unit terkecil dalam Kubernetes yang dapat berisi satu atau lebih container.
- **Services**: Abstraksi untuk mendefinisikan cara mengakses set pod tertentu.
- **Replication Controllers**: Memastikan jumlah pod yang tepat berjalan.
- **Deployments**: Manajemen deklaratif untuk menyebarkan aplikasi.
- **Namespaces**: Isolasi logis untuk sumber daya dalam kluster.
- **Persistent Storage**: Integrasi dengan berbagai penyedia penyimpanan untuk data persisten.
- **ConfigMaps dan Secrets**: Manajemen konfigurasi dan informasi sensitif.

### Manfaat Kubernetes:

- **Skalabilitas**: Otomatis menyesuaikan skala aplikasi berdasarkan beban.
- **Manajemen Rollout/Rollback**: Mengelola rilis aplikasi dan mundur jika terjadi kesalahan.
- **Pemulihan Mandiri**: Secara otomatis me-restart, memindahkan, atau menggantikan container yang gagal.
- **Orkestrasi Lintas Host**: Mengelola deployment aplikasi di beberapa host sebagai satu entitas.

## Cara Kerja Bersama

Docker dan Kubernetes sering digunakan bersama untuk memberikan solusi lengkap dalam manajemen container:

- Docker digunakan untuk membuat dan mengemas aplikasi ke dalam container.
- Kubernetes digunakan untuk mengatur container tersebut dalam skala besar, mengelola lifecycle, dan menyediakan fitur-fitur seperti load balancing, pemulihan diri, dan penskalaan otomatis.

## Contoh Kasus Penggunaan

- **Pengembangan dan Pengujian**: Docker memungkinkan pengembang untuk menjalankan lingkungan pengembangan yang konsisten di mana saja.
- **Produksi dan Orkestrasi**: Kubernetes mengelola container Docker di lingkungan produksi, menangani skala dan pemulihan otomatis.

Dengan memahami peran masing-masing teknologi ini, organisasi dapat merancang dan menjalankan aplikasi yang lebih fleksibel, skala, dan tahan lama.