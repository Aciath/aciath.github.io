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

atau kita juga bisa mencari referensi image di docker hub, yaitu repository image official docker untuk mendownload dan mengupload images .

teman-teman bisa search di browser kesayangan kalian 

`
https://hub.docker.com/
`

Setelah menemukan nama image yang diinginkan download/pull misal dengan perintah

`
docker pull centos
`

Tunggu hingga selesai mendownload imagenya.
