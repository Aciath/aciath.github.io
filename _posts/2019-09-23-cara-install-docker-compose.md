---
layout: post
title:  "cara install docker compose"
date:   2019-09-23 06:20:00 +0700
categories: [docker, devops]
---


## Instalasi Docker Compose
Setelah melakukan instalasi docker engine atau core docker, langkah selanjutnya kita akan melakukan instalasi docker compose, apa itu docker compose?

`
Docker compose berfungsi untuk menjalankan container docker secara bersamaan.
`

docker compose ini sangat berguna ketika aplikasi kita terpisah - pisah pada komputer yang berbeda, contohnya adalah aplikasi yang dibuat berada pada 1 container sedangkan database yang akan digunakan oleh aplikasi tersebut berada pada container yang lain. Ketika menggunakan docker compose maka kita dapat menjalankan kedua container tersebut secara bersamaan dan bahkan kita dapat melakukan link ke container yang kita inginkan.

Untuk melakukan instalasi docker compose silahkan jalankan perintah berikut untuk melakukan akses root.

````
sudo -s
````
kemudian jalankan perintah berikut.


```
curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```

Setelah selesai lalu beri hak akses eksekusi dengan perintah.

```
chmod +x /usr/local/bin/docker-compose
```

Lalu agar docker compose dapat diakses tanpa root, silahkan jalankan perintah berikut.

```
sudo chmod -R 777 /usr/local/bin/docker-compose
```

Kemudian lakukan pengecekan docker compose dengan perintah

```
docker-compose -version
```

Jika berhasil maka akan muncul output seperti berikut.

`
docker-compose version 1.22.0, build 9e633ef
`

oke sekian gitu aja dari gue, tunggu artikel berikutnya.
