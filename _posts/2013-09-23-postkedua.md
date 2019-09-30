---
layout: post                          # (require) default post layout
title: "Cara Install Docker di Centos 7"                   # (require) a string title
date: 2019-09-30 19:51:02 +0700       # (require) a post date
categories: [Docker, Virtualization]          # (custom) some categories, but makesure these categories already exists inside path of `category/`
tags: [foo, bar]                      # (custom) tags only for meta `property="article:tag"`
image: Broadcast_Mail.png             # (custom) image only for meta `property="og:image"`, save your image inside path of `static/img/_posts`
---

## Pengertian Docker
Docker adalah sebuah project open source yang ditujukan untuk developer atau sysadmin untuk membangun, mengemas, dan menjalankan aplikasi dimana pun di dalam sebuah container. Docker berfungsi sebagai virtualisasi sebuah sistem operasi atau sebuah server atau sebuah web server atau bahkan sebuah database server. Dengan virtualisasi ini, diharapkan developer dapat mengembangkan aplikasi sesuai dengan spesifikasi server.
Mengapa dibutuhkan? Jika kita mengembangkan aplikasi di komputer sendiri, tentu saja aplikasi berjalan dengan baik. Namun apa yang akan terjadi jika server yang menjalankan aplikasi kita memiliki banyak perbedaan spesifikasi dengan komputer kita? Ada kemungkinan aplikasi berjalan tidak optimal atau yang lebih buruk yaitu tidak dapat dijalankan. Oleh karena itu, virtualisasi ini dibutuhkan untuk mempermudah developer untuk mengatur mengenai deployment atau menjalankan aplikasi di server production.

### Beberapa Istilah dalam Docker
Untuk membantu memahami Docker, lo harus tau arti dan fungsi dari pilar-pilar ini.

#### 1. Docker Daemon
#### 2. Docker Images
#### 3. Docker Container
#### 4. Docker Registry
