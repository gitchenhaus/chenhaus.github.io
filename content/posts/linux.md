---
title: linux notes
subtitle:
date: 2024-01-12T12:31:42+08:00
slug: 583bc6c
draft: false
author:
  name:
  link:
  email:
  avatar:
description:
keywords:
license:
comment: false
weight: 0
tags:
  - linux
categories:
  - DevOps
hiddenFromHomePage: false
hiddenFromSearch: false
hiddenFromRss: false
hiddenFromRelated: false
summary:
resources:
  - name: featured-image
    src: featured-image.jpg
  - name: featured-image-preview
    src: featured-image-preview.jpg
toc: true
math: false
lightgallery: false
password:
message:
repost:
  enable: true
  url:

---

## 介紹

### `netstat -tulpn`

顯示所有正在使用的連接和相關的程式名稱，並顯示在哪個埠口正在監聽。`-t` 表示顯示 TCP 連接，`-u` 表示顯示 UDP 連接，`-l` 表示顯示正在監聽的連接，`-p` 表示顯示相關的程式名稱，`-n` 表示以數字格式顯示端口和地址。

```bash
netstat -tulpn
```

### `netstat -an`

顯示所有正在使用的連接，包括 IP 地址和端口號，但不顯示相關的程式名稱。`-a` 表示顯示所有連接，`-n` 表示以數字格式顯示端口和地址。

```bash
netstat -an
```

### `nslookup -type=ns example.com`

使用 DNS 查詢獲取指定域名的 NS（Name Server）紀錄。這條指令顯示了 "example.com" 的 Name Server 記錄。

```bash
nslookup -type=ns example.com
```

### `dig example.com NS`

使用 dig 工具查詢指定域名的 NS（Name Server）紀錄。這條指令顯示了 "example.com" 的 Name Server 記錄。

```bash
dig example.com NS
```

### `dig +cdflag @8.8.8.8 haway.xyz a +short`

使用 dig 工具查詢指定 DNS 伺服器（8.8.8.8）上 "haway.xyz" 的 A（IPv4）紀錄。`+cdflag` 表示不要進行 DNSSEC 驗證，`+short` 表示只顯示 IP 地址。

```bash
dig +cdflag @8.8.8.8 haway.xyz a +short
```

### `dig +tcp +short blog.rsync.tw a`

使用 dig 工具通過 TCP 協議查詢 "blog.rsync.tw" 的 A（IPv4）紀錄，同時只顯示 IP 地址。

```bash
dig +tcp +short blog.rsync.tw a
```

### `dig rsync.tw mx`

使用 dig 工具查詢 "rsync.tw" 的 MX（Mail Exchange）紀錄，顯示郵件伺服器的信息。

```bash
dig rsync.tw mx
```

### `dig rsync.tw soa`

使用 dig 工具查詢 "rsync.tw" 的 SOA（Start of Authority）紀錄，顯示主權區的相關信息。

```bash
dig rsync.tw soa
```

### `dig -x 8.8.8.8 ptr`

使用 dig 工具查詢指定 IP 地址（8.8.8.8）的 PTR（Pointer）紀錄，顯示逆向 DNS 查詢的結果。

```bash
dig -x 8.8.8.8 ptr
```

### `dig +trace blog.rsync.tw a`

使用 dig 工具以追踪模式查詢 "blog.rsync.tw" 的 A（IPv4）紀錄，顯示 DNS 查詢的過程。

```bash
dig +trace blog.rsync.tw a
```

### `telnet ip_address port_number`

使用 telnet 工具建立到指定 IP 地址和端口號的 TCP 連接，用於測試網絡連通性。

```bash
telnet ip_address port_number
```

### `nc -vz amazon.com 80`

使用 nc（netcat）工具測試到指定主機（amazon.com）的指定端口（80）是否可連接。`-v` 表示詳細模式，`-z` 表示僅檢查連接是否成功。

```bash
nc -vz amazon.com 80
```

### `nmap -p <port_number> <ip_address>`

使用 nmap 工具掃描指定 IP 地址上的指定端口號，顯示端口的狀態。可以使用 `<port_number>` 和 `<ip_address>` 替換實際的端口號和 IP 地址。

```bash
nmap -p <port_number> <ip_address>
```

### `nmap -p 1-100 <ip_address>`

使用 nmap 工具掃描指定 IP 地址上的端口範圍（1 到 100），顯示端口的狀態。

```bash
nmap -p 1-100 <ip_address>
```

### `ulimit -n`

顯示用戶進程的文件描述符限制數量。

```bash
ulimit -n
```

### `ulimit -nH`

顯示用戶進程的文件描述符硬限制數量。

```bash
ulimit -nH
```

### `/etc/sysctl.conf`

這是一個配置文件，包含有關系統內核參數的配置。你可以使用這個文件調整系統的各種參數。

```bash
cat /etc/sysctl.conf
```

### `cat /proc/sys/fs/file-max`

顯示系統內核中的文件描述符上限。

```bash
cat /proc/sys/fs/file-max
```

### `du -hc --max-depth=0`

顯示當前目錄的總大小，`--max-depth=0` 表示僅顯示當前目錄而不深入子目錄。

```bash
du -hc --max-depth=0
```

### `sudo du -h -d 1 | sort -h`

使用 sudo 權限顯示當前目錄中的所有子目錄的大小，按大小排序。

```bash
sudo du -h -d 1 | sort -h
```

### `jps -l`

顯示正在運行的 Java 進程及其完整包名稱或 JAR 檔案路徑。這個指令對於查看當前運行的 Java 應用程式非常有用。

```bash
jps -l
```

<!--more-->
