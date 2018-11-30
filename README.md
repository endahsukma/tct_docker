# Pertemuan ke 11
---
*Endah Sukma Kuncari*
---
Kata Koda

First Docker Container
1. Menjalankan kontainer
	*docker search redis*
	Untuk menemukan gambar untuk redis
	![]()
	*docker run -d redis*
	docker akan menjalankan versi terbaru dari radis
	*docker ps*
	![]()
2. Menemukan kontainer yang sedang berjalan
	docker ps
	perintah ini dapat digunakan untuk menampilkan nama dan id yang dapat untuk mencari
	![]()
	informasi container
3. Akses redis
	*docker run -d --name redisHostPort -p 6379:6379 redis:latest*
	merupakan cara menyelesaikan masalah background radis dengan nama redisHostPort 6379
	![]()
	*docker run -d --name redisDynamic -p 6379 redis:latest*
	dengan mengunakan opsi -p 6379 untuk memungkinkan mengekspos redis tetapi pada port
	yang tersedia secara acak
	![]()
	*docker port redisDynamic 6379*
	Untuk mengetahui port yang akan dikerjakan
	![]()
	*docker ps*
	Informasi port
	![]()
4. Data yang bertahan
	*docker run -d --name redisMapped -v /opt/docker/data/redis:/data redis*
	Menggunakan dokumentasi Hub Docker untuk Redis
	![]()
	*docker run ubuntu ps*
	container ubuntu dan mengeksekusi perintah ps untuk melihat berjalannya proses dalam suatu container
	![]()
	*docker run -it ubuntu bash*
	untuk mendapatkan akses shell bash pada container
	![]()

---
Deploy Static
1. Membuat Dockerfile
Dockerfile adalah daftar instruksi yang menjelaskan cara menyebarkan aplikasi Anda.
FROM nginx:alpine
COPY . /usr/share/nginx/html
![]()

2. Membangun image docker
*docker build -t webserver-image:v1 .*
Static html image
![]()
*docker images*
nama webserver-image dengan tag v1
![]()

3. Run
*docker run -d -p 80:80 webserver-image:v1*
![]()
*curl docker*
server web, bind port 80 ke host menggunakan parameter -p.
![]()

---
Docker 2
1. Base Images
*FROM nginx:1.11-alpine*
dockfile harus dari nginx:1.11-alpine
![]()
2. Running Commands
*COPY index.html /usr/share/nginx/html/index.html*
file name dengan nama index.html
![]()
3. Exposing Ports
*EXPOSE 80*
![]()
4. Building Container Images 
*CMD ["nginx", "-g", "daemon off;"]*
![]()
5. Building Containers
*docker images*
Untuk melihat image yang berada di computer local
![]()
6. Launching New Image
curl -i http://docker
Dapat mengakses webserver docker
![]()
*docker ps*
Untuk mengecek container yang sedang berjalan.
![]()

Untuk Docker ke 3 saya belum dapat mencoba mempraktikan karena pada saat akan memulai skenario tidak terespon.

	