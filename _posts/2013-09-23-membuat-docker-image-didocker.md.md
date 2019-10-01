---
layout: post                          # (require) default post layout
title: "part 3 - Membuat Docker Image di Docker"                   # (require) a string title
date: 2019-09-30 19:51:02 +0700       # (require) a post date
categories: [docker, virtualization, devops]          # (custom) some categories, but makesure these categories already exists inside path of `category/`
tags: [foo, bar]                      # (custom) tags only for meta `property="article:tag"`
image: Broadcast_Mail.png             # (custom) image only for meta `property="og:image"`, save your image inside path of `static/img/_posts`
---
Docker engine telah terinstall, selanjutnya kita bisa mulai membuat sebuah container dengan mendownload docker images di 
 `Docker Registry ` yang merupakan tempat penyimpanan public atau privat untuk mendownload dan mengupload images.

Contoh kita akan mendownload docker image centos
Untuk mencari image

`
$ docker search centos
`


![csr config](https://raw.githubusercontent.com/aciath/aciath.github.io/master/static/img/_posts/part3.png)



atau kita juga bisa mencari referensi image di docker hub, yaitu repository image official docker untuk mendownload dan mengupload images .

teman-teman bisa search di browser kesayangan kalian 

`
https://hub.docker.com/
`
![csr config](https://raw.githubusercontent.com/aciath/aciath.github.io/master/static/img/_posts/dockerhub.png)

Setelah menemukan nama image yang diinginkan download/pull misal dengan perintah

`
docker pull centos
`

Tunggu hingga selesai mendownload imagenya.
Kemudian coba jalankan docker container, dan masuk ke shellnya

`
docker run -i -t centos /bin/bash
`

![csr config](https://raw.githubusercontent.com/aciath/aciath.github.io/master/static/img/_posts/part3-1.png)


Ketik “exit” untuk keluar, kemudian kita coba cek containernya dengan perintah

`
docker ps -a
`

![csr config](https://raw.githubusercontent.com/aciath/aciath.github.io/master/static/img/_posts/part3-2.png)


Akan tampak 1 nama container, karena kita me-run 1 perintah diatas, coba kembali jalankan perintah 

`
docker run -i -t centos /bin/bash
`

masuk ke dalam shell lagi, lalu coba buat sebuah file atau perubahan lainnya dan simpan, kemudian anda coba keluar dengan “exit”.
Lihat lagi daftar containernya

`
docker ps -a
`

hasilnya akan terlihat


![csr config](https://raw.githubusercontent.com/aciath/aciath.github.io/master/static/img/_posts/part3-3.png)


Ada tambahan 1 container lagi berarti jumlahnya ada 2, jadi setiap kita melakukan perubahan image otomatis docker akan membuat sebuah container baru dengan otomatis juga menambahkan nama dan ID baru. Kita juga dapat kembali ke container yang telah kita lakukan perubahan sebelumnya dan meneruskannya dengan perintah

`
docker start [container ID]
`

`
docker attach [container ID]
`

Cek info versi docker
`
docker info
`

Mengunduh images dari Docker hub

`
docker pull [image name]
`

Menghapus image dalam docker

`
docker rmi [image ID]
`

Melihat daftar image

`
docker images
`

Membuat container baru

`
docker run [image name] [command to run]
`
Menyetop container
`
docker stop [container ID]
`
Start container

`
docker start [container ID]
`

Melihat daftar kontainer

`
docker ps
`

Menghapus kontainer yang ada

`
docker rm [container ID]
`

Melakukan commit perubahan pada images

`
docker commit [container ID] [image name]
`

Oke semoga bermanfaat ya ...........
