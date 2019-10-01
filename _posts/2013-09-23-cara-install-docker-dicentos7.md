---
layout: post                          # (require) default post layout
title: "part 1 - Cara Install Docker di Centos 7"                   # (require) a string title
date: 2019-09-30 19:51:02 +0700       # (require) a post date
categories: [docker, virtualization, devops]          # (custom) some categories, but makesure these categories already exists inside path of `category/`
tags: [foo, bar]                      # (custom) tags only for meta `property="article:tag"`
image: Broadcast_Mail.png             # (custom) image only for meta `property="og:image"`, save your image inside path of `static/img/_posts`
---

## Pengertian Docker
Docker adalah sebuah project open source yang ditujukan untuk developer atau sysadmin untuk membangun, mengemas, dan menjalankan aplikasi dimana pun di dalam sebuah container. Docker berfungsi sebagai virtualisasi sebuah sistem operasi atau sebuah server atau sebuah web server atau bahkan sebuah database server. Dengan virtualisasi ini, diharapkan developer dapat mengembangkan aplikasi sesuai dengan spesifikasi server.
Mengapa dibutuhkan? Jika kita mengembangkan aplikasi di komputer sendiri, tentu saja aplikasi berjalan dengan baik. Namun apa yang akan terjadi jika server yang menjalankan aplikasi kita memiliki banyak perbedaan spesifikasi dengan komputer kita? Ada kemungkinan aplikasi berjalan tidak optimal atau yang lebih buruk yaitu tidak dapat dijalankan. Oleh karena itu, virtualisasi ini dibutuhkan untuk mempermudah developer untuk mengatur mengenai deployment atau menjalankan aplikasi di server production.

### Beberapa Istilah dalam Docker
Untuk membantu memahami Docker, lo harus tau arti dan fungsi dari pilar-pilar ini.

#### 1. Docker Daemon
Docker daemon adalah sebuah service yang dijalankan di dalam host dalam Operating System (OS) kita. Fungsinya adalah membangun, mendistribusikan, dan menjalankan container docker. Pengguna tidak dapat langsung menggunakan docker daemon, akan tetapi untuk menggunakan docker daemon maka pengguna menggunakan docker client sebagai perantara atau CLI.
#### 2. Docker Images
Docker images adalah sebuah template yang bersifat read only. Template ini sebenarnya adalah sebuah OS atau OS yang telah diinstall berbagai aplikasi. Fungsi dari docker images sendiri adalah membuat docker container, hanya dengan satu docker image kita dapat membuat banyak docker container.
#### 3. Docker Container
Docker container bisa dianggap sebagai sebuah folder, docker container dibuat menggunakan docker daemon. Docker container ini nantinya dapat dibuild sehingga akan menghasilkan sebuah docker image dan docker image yang dihasilkan dari docker container ini dapat kita gunakan kembali untuk membuat docker container yang baru.
#### 4. Docker Registry
Docker registry adalah kumpulan docker image yang bersifat private maupun public yang dapat anda akses di `docker hub`. Kita dapat push atau pull image kita sendiri di sini.

![csr config](https://raw.githubusercontent.com/aciath/aciath.github.io/master/static/img/_posts/docker-infra.png)

#### 5. Docker/Container Orchestration
adalah suatu kegiatan mengatur siklus hidup dari container, terutama dalam environment yang besar dan dinamis. Developer dapat menggunakan container orchestration untuk mengontrol dan mengautomasi banyak pekerjaan seperti:
Proses mulai dan berhentinya container.
Mengekspos fungsionalitas dari container ke user atau container lainnya.
Memonitor dan merespon perilaku container.
Mendeploy container versi baru dengan zero-downtime.
Pembersihan secara auto maupun manual.
Tool yang digunakan untuk docker/container orchestration salah satunya adalah docker swarm dan kubernetes.

## Instalasi Docker

#### 1. `install paket yum-utils, device-mapper-persistent-data dan lvm2`
```
$ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```
#### 2. Ketika anda menginginkan versi stable dari docker, tambahkan repository berikut :

````
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
````
#### 3. Untuk konfigurasi opsional, bisa mengaktifkan repository versi edge dan test dengan :
```
$ sudo yum-config-manager --enable docker-ce-edge
$ sudo yum-config-manager --enable docker-ce-test
```
#### 4. Nah, tinggal install docker-ce nya dengan perintah :
```
$ sudo yum install docker-ce
```
`Note : accept GPG key, verifikasi 060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35`
#### 5. Setelah install docker-ce. layanan tidak otomatis running karena belum ada satu userpun yang ditambahkan ke group docker. Untuk menjalankannya bisa dengan perintah :
```
$ sudo systemctl start docker
```
#### 6. Untuk mem-verifikasi bahwa layanan docker sudah terinstall dengan baik yaitu bisa menjalankan hello-world image.
```
$ sudo docker run hello-world
```
