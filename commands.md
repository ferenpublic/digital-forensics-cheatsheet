### Hak Akses Root
Masuk sebagai user root untuk menjalankan perintah yang membutuhkan hak administrator.

```bash
sudo su
```

### Melihat Uptime Sistem
Menampilkan waktu saat ini, lama sistem aktif, user yang login, dan load average.

```bash
w
```

### Riwayat Login User
Menampilkan riwayat login, logout, IP asal, dan durasi sesi pengguna.

```bash
last -a
```

### Melihat Koneksi Jaringan Aktif
Menampilkan koneksi TCP/UDP, port yang aktif, dan service yang berjalan.

```bash
netstat
```

### Install Netstat (net-tools)
Menginstal package net-tools jika perintah netstat belum tersedia.

```bash
apt install -y net-tools
```

### Melihat Open Files
Menampilkan file yang sedang digunakan proses dan menyimpan hasil ke file.

```bash
lsof > openfiles.txt
```

### Membuka Hasil Open Files
Membuka file hasil investigasi menggunakan editor teks.

```bash
gedit openfiles.txt
```

### Melihat Kernel Module Aktif
Menampilkan seluruh kernel module yang sedang dimuat.

```bash
lsmod
```

### Install Audit Framework
Menginstal auditd untuk logging dan monitoring aktivitas sistem.

```bash
apt install -y auditd
```

### Menampilkan Audit Report
Menampilkan laporan aktivitas keamanan dan audit sistem.

```bash
aureport
```

### Mengetahui User ID (UID)
Menampilkan UID, GID, dan grup milik user.

```bash
id james
```

### Melacak Aktivitas Berdasarkan UID
Mencari aktivitas audit berdasarkan User ID tertentu.

```bash
ausearch -ui 1000 --interpret
```

### Lokasi Cron User
Direktori penyimpanan cron job milik user.

```bash
/var/spool/cron/
```

### Lokasi Cron Harian
Direktori cron job yang dijalankan setiap hari.

```bash
/etc/cron.daily
```

### Melihat Bash History
Melihat riwayat command yang pernah dijalankan user.

```bash
gedit ~/.bash_history
```

### Melihat ARP Cache
Menampilkan pasangan IP Address dan MAC Address yang tersimpan.

```bash
arp
```

### Melihat Running Process
Menampilkan seluruh proses yang sedang berjalan beserta detailnya.

```bash
ps auxww
```

### Mengetahui Port dari Process Tertentu
Menampilkan port yang digunakan oleh PID tertentu.

```bash
ss -l -p -n | grep PID
```

Contoh:

```bash
ss -l -p -n | grep 1234
```

### Install Grep
Menginstal grep jika belum tersedia.

```bash
apt-get install grep
```

### Investigasi Direktori /proc
Masuk ke direktori informasi live sistem dan menampilkan isinya.

```bash
cd /proc
ls
```

### Melihat Isi Clipboard
Menampilkan data terakhir yang disalin ke clipboard.

```bash
xclip -o
```

### Install xclip
Menginstal utilitas xclip.

```bash
apt install xclip
```

### Mengetahui Hostname Sistem
Menampilkan nama host/komputer saat ini.

```bash
hostname
```

### Install Nmap
Menginstal tool Nmap untuk scanning port.

```bash
apt install nmap
```

### Scan Open TCP Port
Melakukan pemindaian port TCP yang terbuka pada localhost.

```bash
nmap -sT localhost
```

### Scan Open UDP Port
Melakukan pemindaian port UDP yang terbuka pada localhost.

```bash
nmap -sU localhost
```

### Melihat Versi Kernel Linux
Menampilkan versi kernel Linux yang sedang digunakan.

```bash
uname -r
```

### Melihat Seluruh User Account
Menampilkan informasi seluruh akun pengguna yang terdaftar pada sistem.

```bash
cat /etc/passwd
```

### Melihat Informasi Password Hash User
Menampilkan data autentikasi dan password hash user (butuh hak root).

```bash
cat /etc/shadow
```

### Menampilkan Daftar Username Saja
Mengambil hanya nama pengguna tanpa informasi lainnya.

```bash
cut -d: -f1 /etc/passwd
```

### Melihat Riwayat Login Sistem dari File WTMP
Menampilkan histori login, logout, dan reboot sistem.

```bash
last -f /var/log/wtmp.db
```

### Melihat Authentication Log
Menampilkan aktivitas autentikasi seperti login, sudo, SSH, dan gagal login.

```bash
cat /var/log/auth.log
```