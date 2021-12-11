# Jarkom-Modul-5-B11-2021

## **Kelompok B-11**

|      NRP       |         Nama          |
| :------------: | :-------------------: |
| 05111940000079 |    Muhammad Nevin     |
| 05111940000116 | Albert Filip Silalahi |
| 05111940000132 | Jagad Wijaya Purnomo  |

## Topologi
![topologi](https://user-images.githubusercontent.com/31863229/144903369-1fe4329a-3fcf-4a49-b655-fff029c30dd6.PNG)

## Subnetting (CIDR)
**Langkah 1**
![subnetting_01](https://user-images.githubusercontent.com/31863229/144903254-3af2f1e8-08b5-4fb6-b83c-bcf9e8d139ef.png)

**Langkah 2**
![subnetting_02](https://user-images.githubusercontent.com/31863229/144903297-f4268c43-8089-4d77-9f0d-735ba4c19678.png)

**Langkah 3**
![subnetting_03](https://user-images.githubusercontent.com/31863229/144903316-ceb0378e-db57-4339-b979-9ffac0af660c.png)

**Langkah 4**
![subnetting_04](https://user-images.githubusercontent.com/31863229/144903322-7ed6a7c0-a29c-4c65-80ab-ecc521718c1c.png)

**Langkah 5**
![subnetting_05](https://user-images.githubusercontent.com/31863229/144903336-5ac08b4c-b1d9-46de-b957-4ebd6e8d197f.png)

**Hasil subnetting**
![subnetting_06](https://user-images.githubusercontent.com/31863229/144903344-2e9f3397-994c-49b6-ac5a-278e943d1d6c.png)

**CIDR Tree**

## Setting GNS3
**FOOSHA (sebagai Router / DHCP Relay)**
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 191.182.8.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 191.182.20.1
	netmask 255.255.255.252
```

**WATER7 (sebagai Router / DHCP Relay)**
```
auto eth0
iface eth0 inet static
	address 191.182.8.2
	netmask 255.255.255.252
	gateway 191.182.8.1

auto eth1
iface eth1 inet static
	address 10.151.79.105
	netmask 255.255.255.248

auto eth2
iface eth2 inet static
	address 191.182.0.1
	netmask 255.255.255.128

auto eth3
iface eth3 inet static
	address 191.182.4.1
	netmask 255.255.252.0
```

**GUANHAO (sebagai Router / DHCP Relay)**
```
auto eth0
iface eth0 inet static
	address 191.182.20.2
	netmask 255.255.255.252
	gateway 191.182.20.1

auto eth1
iface eth1 inet static
	address 191.182.17.1
	netmask 255.255.255.248

auto eth2
iface eth2 inet static
	address 191.182.18.1
	netmask 255.255.254.0

auto eth3
iface eth3 inet static
	address 191.182.16.1
	netmask 255.255.255.0
```

**DORIKI (sebagai DNS Server)**
```
auto eth0
iface eth0 inet static
	address 10.151.79.106
	netmask 255.255.255.248
	gateway 10.151.79.105
```

**JIPANGU (sebagai DHCP Server)**
```
auto eth0
iface eth0 inet static
	address 10.151.79.107
	netmask 255.255.255.248
	gateway 10.151.79.105
```

**JORGE (sebagai Web Server)**
```
auto eth0
iface eth0 inet dhcp
```

**MAINGATE (sebagai Web Server)**
```
auto eth0
iface eth0 inet dhcp
```

**BLUENO (sebagai Client)**
```
auto eth0
iface eth0 inet dhcp
```

**CIPHER (sebagai Client)**
```
auto eth0
iface eth0 inet dhcp
```

**ELENA (sebagai Client)**
```
auto eth0
iface eth0 inet dhcp
```

**FUKUROU (sebagai Client)**
```
auto eth0
iface eth0 inet dhcp
```

## Routing
**FOOSHA**
```
route add -net 10.151.79.104 netmask 255.255.255.248 gw 191.182.8.2
route add -net 191.182.0.0 netmask 255.255.240.0 gw 191.182.8.2
route add -net 191.182.16.0 netmask 255.255.248.0 gw 191.182.20.2
```

## Soal 1
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Foosha menggunakan iptables, tetapi Luffy tidak ingin menggunakan MASQUERADE.

### Jawaban


## Soal 2
Kalian diminta untuk mendrop semua akses HTTP dari luar Topologi kalian pada server yang merupakan DHCP Server dan DNS Server demi menjaga keamanan.


### Jawaban


## Soal 3
Karena kelompok kalian maksimal terdiri dari 3 orang. Luffy meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 3 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.


### Jawaban


## Soal 4
Akses dari subnet Blueno dan Cipher hanya diperbolehkan pada pukul 07.00 - 15.00 pada hari Senin sampai Kamis

### Jawaban


## Soal 5
Akses dari subnet Elena dan Fukuro hanya diperbolehkan pada pukul 15.01 hingga pukul 06.59 setiap harinya.
Selain itu di reject


### Jawaban


## Soal 6
Karena kita memiliki 2 Web Server, Luffy ingin Guanhao disetting sehingga setiap request dari client yang mengakses DNS Server akan didistribusikan secara bergantian pada Jorge dan Maingate

### Jawaban
