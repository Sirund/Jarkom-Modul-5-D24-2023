# Jarkom-Modul-5-D24-2023
# Anggota Kelompok
|                Nama                |    NRP     |
| :--------------------------------: | :--------: |
|            Daffa Saskara           | 5025211249 |
|      Arundaya Pratama Nurhasan     | 5025221203 |

## Topologi
Dibawah ini adalah opologi yang digunakan untuk praktikum modul 5 adalah sebagai berikut.
![topologi_modul_5](https://github.com/Sirund/Jarkom-Modul-5-D24/assets/120204570/93336f4a-bb83-4984-8de1-806b9eeea3ea)

## Subneting

**Penjelasan**
Untuk melakukan subneting pada praktikum 5 ini kita menggunakan metode VLSM 
Berikut adalah topologi pengelompokan subnet :

![Screenshot from 2023-12-21 14-14-00](https://github.com/Sirund/Jarkom-Modul-5-D24/assets/120204570/fd36f636-9e84-4007-ad53-86c8d4fe9634)

Setelah kita membuat pengelompokan subnet selanjutnya kita buat tabel pengelompokan subnet dan melakukan perhitungan dengan VLSM kita mendapat pembagian ip sebagai berikut:

![Screenshot from 2023-12-21 14-37-14](https://github.com/Sirund/Jarkom-Modul-5-D24/assets/120204570/49f86e45-f056-49ca-89f8-f219140e2873)

## Routing 
sebelum kita melakukan routing kia melakukan IP configuration dulu di gns3 yang telah kita buat berikut adalah configurasinya : 

Revolte :
```bash
auto eth0
iface eth0 inet static
address 192.203.0.2
netmask 255.255.255.252
gateway 192.203.0.1
```

Ritcher : 
```bash
auto eth0
iface eth0 inet static
address 192.203.0.6
netmask 255.255.255.252
gateway 192.203.0.5
```

Stark :
```bash
auto eth0
iface eth0 inet static
address 192.203.0.18
netmask 255.255.255.252
gateway 192.203.0.17
```

Sein : 
```bash
auto eth0
iface eth0 inet static
address 192.203.4.2
netmask 255.255.252.0
gateway 192.203.4.1
```

TurkRegion : 
```bash
auto eth0
iface eth0 inet dhcp
address 192.203.8.2
netmask 255.255.248.0
gateway 192.203.8.1
```

GrobeForest : 
```bash
auto eth0
iface eth0 inet dhcp
address 192.203.4.3
netmask 255.255.252.0
gateway 192.203.4.1
```

SchwerMotain : 
```bash
auto eth0
iface eth0 inet dhcp
address 192.203.0.131
netmask 255.255.255.128
gateway 192.203.0.129
```

LaubHills: 
```bash
auto eth0
iface eth0 inet dhcp
address 192.203.2.2
netmask 255.255.254.0
gateway 192.203.2.1
```

Aura : 
```bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 192.203.0.25
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 192.203.0.21
netmask 255.255.255.252
```

Heiter : 
```bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.203.0.26
netmask 255.255.255.252

auto eth1
iface eth1 inet static
address 192.203.8.1
netmask 255.255.248.0

auto eth2
iface eth2 inet static
address 192.203.4.1
netmask 255.255.252.0
```

Frieren 
```bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.203.0.22
netmask 255.255.255.252

auto eth1
iface eth1 inet static
address 192.203.0.17
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 192.203.0.13
netmask 255.255.255.252
```

Himmel : 
```bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.203.0.14
netmask 255.255.255.252

auto eth1
iface eth1 inet static
address 192.203.2.1
netmask 255.255.254.0

auto eth2
iface eth2 inet static
address 192.203.0.129
netmask 255.255.255.128
```

Fern : 
```bash
auto lo
iface lo inet loopback

auto eth2
iface eth2 inet static
address 192.203.0.1
netmask 255.255.255.252

auto eth1
iface eth1 inet static
address 192.203.0.5
netmask 255.255.255.252

auto eth0
iface eth0 inet static
address 192.203.0.130
netmask 255.255.255.128
```

Setelah menentukan Ip kita lakukan touting di setiap Router yang ada, berikut adalah code untuk setiap routernya :

Fern : 
```bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.203.0.129
```

Himmel : 
```bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.203.0.13

route add -net 192.203.0.0 netmask 255.255.255.252 gw 192.203.0.130
route add -net 192.203.0.4 netmask 255.255.255.252 gw 192.203.0.130
```

Frieren : 
```bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.203.0.21

route add -net 192.203.2.0 netmask 255.255.254.0 gw 192.203.0.14
route add -net 192.203.0.128 netmask 255.255.255.128 gw 192.203.0.14
route add -net 192.203.0.0 netmask 255.255.255.252 gw 192.203.0.14
route add -net 192.203.0.4 netmask 255.255.255.252 gw 192.203.0.14
```

Heiter 
```bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.203.0.25
```

Aura 
```bash
# Heiter
route add -net 192.203.4.0  netmask 255.255.252.0 gw 192.203.0.26
route add -net 192.203.8.0  netmask 255.255.248.0  gw 192.203.0.26

# Frieren
route add -net 192.203.0.16 netmask 255.255.255.252 gw 192.203.0.22
route add -net 192.203.0.12 netmask 255.255.255.252 gw 192.203.0.22
route add -net 192.203.2.0 netmask 255.255.254.0 gw 192.203.0.22
route add -net 192.203.0.128 netmask 255.255.255.128 gw 192.203.0.22
route add -net 192.203.0.7 netmask 255.255.255.252 gw 192.203.0.22
route add -net 192.203.0.0 netmask 255.255.255.252 gw 192.203.0.22
```

## Nomor 1
**Soal**

Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

**Penjelasan**

Untuk membuat konfigurasi Aura menggunakan iptable, tetapi tidak ingin menggunakan MASQUERADE yaitu dengan masukkan perintah berikut : 

```
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')

iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```

perintah `ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}`  berfungsi untuk mengembalikan IP eth0 Aura 

Selanjutnya, untuk menyambungkan ke nat, maka kita masukkan ke NAT Table dengan POSTROUTING chain : `iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP`

## Nomor 2
**Soal**

Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

**Penyelesaian**

pertama tama kita install netcat pada router `Aura` dengan melakukan command sebagai berikut
```bash
apt-get update
apt-get install netcat -y
```
Lalu untuk menolak suma koneksi TCP kecuali port 8080 bisa menggunakan command berikut : 

```bash
iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
iptables -A INPUT -p tcp -j DROP
```

lalu untuk menolak semua koneksi di udp bisa menggunakan command berikut : 
```bash
iptables -A INPUT -p udp -j DROP
```

## Nomor 3
**Soal**
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

**Penyelesaian**
untuk membatasi DHCP dan DNS Server hanya dapat dilakukan oleh maksimal 3 device lakukan perintah berikut di Revolte & Richter DHCP server & DNS Server

```bash
#Allow established and related connections
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
#Limit ICMP connections to 3 per second
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```
- `--connlimit-above 3` adalah parameter menentukan batas koneksi yang terhubung
- `--connlimit-mask 0` adalah parameter menentukan mask

## Nomor 4
**Soal**

Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

**Penyelesaian**
  - Sein & Stark (Web Server)
```bash
iptables -A INPUT -p tcp --dport 22 -s 192.203.4.0/22 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
```

## Nomor 5
**Soal**

Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

**Penyelesaian**
  - Sein & Stark (Web Server)
```bash
# Izinkan akses ke Web Server pada senin-jumat pukul 08:00-16:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
```

## Nomor 6
**Soal**

Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

**Penyelesaian**
  - Konfigurasi Sein & Stark (Web Server)
```bash
# Larangan Akses pada hari Senin-Kamis jam 12:00 - 13:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP

# Larangan akses pada hari jumat pada 11:00 - 13:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
```

## Nomor 7
**Soal**

Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

**Penyelesaian**
  - Sein
```bash
# Soal 7
iptables -A PREROUTING -t nat -p tcp -d 192.203.4.2 --dport 80 -m statistics --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.203.4.2:80

iptables -A PREROUTING -t nat -p tcp -d 192.203.4.2 --dport 80 -j DNAT --to-destination 192.203.0.14:80
```

  - Stark
```bash
# Soal 7
iptables -A PREROUTING -t nat -p tcp -d 192.203.0.4 --dport 443 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.203.4.2:443

iptables -A PREROUTING -t nat tcp -d 192.203.0.4 --dport 443 -j DNAT --to-destination 192.203.0.14:443
```

## Nomor 8
**Soal**

Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

**Penyelesaian**
  - Sein
```bash
### apabila ingin meng-drop TCP 
iptables -A INPUT -p tcp -s 192.203.0.2 --dport 80 -m time --datestart 2023-10-19T00:00 --datestop 2024-02-15T00:00 -j DROP

### namun ingin drop semua, bisa digunakan :
iptables -A INPUT -s 192.203.0.2 -m time --datestart 2023-10-19T00:00 --datestop 2024-02-15T00:00 -j DROP

```

## Nomor 9
**Soal**

Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. (clue: test dengan nmap)

**Penyelesaian**
  - Sein
```bash
iptables -A INPUT -p tcp --syn -m recent --name portscan --set
iptables -A INPUT -p tcp --syn -m recent --name portscan --rcheck --seconds 600 --hitcount  20  -j  DROP
```

  - Stark
```bash
iptables -N PORTSCAN
iptables -A PORTSCAN -m recent --set --name portscan
iptables -A PORTSCAN -m recent --update --seconds 600 --hitcount 20 --name portscan -j LOG --log-prefix "Portscan Detected: " --log-level 4
iptables -A PORTSCAN -m recent --update --seconds 600 --hitcount 20 --name portscan -j DROP
iptables -A INPUT -p tcp --tcp-flags SYN,ACK,FIN,RST RST -m limit --limit 2/s -j ACCEPT
iptables -A INPUT -p tcp --tcp-flags SYN,ACK,FIN,RST RST -j PORTSCAN
```

## Nomor 10
**Soal**

Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.

**Penyelesaian**

logging dapat ditambahkan dengan syntax iptables berikut yang dijalankan di semua node server dan router

```bash
iptables -A INPUT -j LOG --log-level debug --log-prefix "Dropped Packet: " -m limit --limit 1/second --limit-burst 10
```
