# Gunakan image resmi Nginx sebagai base image
FROM nginx:1-alphine=slim

# Salin konfigurasi Nginx ke dalam image
COPY nginx.conf /etc/nginx/nginx.conf

# Salin seluruh folder meyawo-template ke dalam direktori default Nginx
COPY meyawo-template/* /usr/share/nginx/html/

# Jalankan Nginx ketika container dijalankan
CMD ["nginx", "-g", "daemon off;"]
