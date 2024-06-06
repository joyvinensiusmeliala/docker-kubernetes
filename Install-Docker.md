# Dokumentasi Lengkap: Instalasi Docker di Ubuntu

## Prasyarat

- Ubuntu 18.04 atau versi lebih baru.
- Akses sudo atau akses root.

## Langkah 1: Update Sistem

Perbarui daftar paket sistem agar Anda memiliki versi terbaru dari paket yang tersedia.

```sh
sudo apt-get update
```

## Langkah 2: Install Prasyarat

Instal paket yang diperlukan untuk memungkinkan APT menggunakan repositori melalui HTTPS.

```sh
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
```

## Langkah 3: Tambahkan Kunci GPG Resmi Docker

Tambahkan kunci GPG Docker ke sistem Anda untuk memastikan integritas paket yang diunduh.

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

## Langkah 4: Tambahkan Repositori Docker

Tambahkan repositori Docker ke daftar sumber APT Anda. Perintah ini akan memastikan Anda mengunduh Docker dari repositori resmi Docker.

```sh
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

## Langkah 5: Perbarui Daftar Paket Lagi

Perbarui daftar paket lagi untuk menyertakan repositori Docker yang baru ditambahkan.

```sh
sudo apt-get update
```

## Langkah 6: Install Docker

Instal Docker CE (Community Edition) menggunakan perintah berikut.

```sh
sudo apt-get install -y docker-ce   
```

## Langkah 7: Verifikasi Instalasi Docker

Verifikasi bahwa Docker telah diinstal dengan benar dengan menjalankan perintah berikut.

```sh
sudo docker run hello-world
```

Perintah ini akan mengunduh dan menjalankan image tes Docker. Jika semuanya berfungsi dengan baik, Anda akan melihat pesan selamat datang dari Docker.

## Langkah 8: (Opsional) Menjalankan Docker Tanpa Sudo

Jika Anda ingin menjalankan perintah Docker tanpa menggunakan sudo, Anda dapat menambahkan pengguna Anda ke grup Docker.

Tambahkan pengguna Anda ke grup Docker.

```sh
sudo usermod -aG docker $USER 
```

Log out dan log back in agar perubahan grup berlaku.

```sh
exit
```

Log in kembali ke sistem Anda dan verifikasi bahwa Anda dapat menjalankan Docker tanpa sudo.

```sh
docker run hello-world
```

## Langkah 9: Mengatur Docker untuk Mulai pada Boot

Agar Docker secara otomatis mulai saat sistem di-boot, jalankan perintah berikut:

```sh
sudo systemctl enable docker
```

## Langkah 10: Verifikasi Versi Docker

Pastikan instalasi Docker berhasil dengan memeriksa versi Docker yang terinstal.

```sh
docker --version
```

Ini akan menampilkan versi Docker yang terinstal, memastikan instalasi telah berhasil.

## Troubleshooting

Jika Anda mengalami masalah selama instalasi, berikut beberapa langkah pemecahan masalah:

-  Cek Status Layanan Docker: Periksa apakah layanan Docker berjalan dengan baik.

```sh
sudo systemctl status docker
```

- Lihat Log Docker: Jika layanan Docker tidak berjalan, periksa log untuk informasi lebih lanjut.

```sh
sudo journalctl -u docker
```

- Reinstall Docker: Jika masalah tetap ada, Anda mungkin perlu menghapus dan menginstal ulang Docker.


```sh
sudo apt-get remove docker-ce
sudo apt-get purge docker-ce
sudo apt-get autoremove
sudo rm -rf /var/lib/docker
sudo rm -rf /etc/docker
```