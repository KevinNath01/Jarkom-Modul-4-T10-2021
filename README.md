# Jarkom-Modul-4-T10-2021

PRAKTIKUM MODUL 4 JARINGAN KOMPUTER 2021

Anggota Kelompok T10:<br>

1. Tri Rizki Yuliawan (05311940000024) <br>
2. Kevin Nathaniel (05311940000032) <br>
3. I Gde Ardha Semaranatha Gunasatwika (05311940000034) <br>

# Soal <a name="Soal"></a>

### 1. VLSM

**Diagram**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/PembagianVLSM.png">
<br>

**Tree**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/TreeVLSM.jpg">
<br>
**Tabel**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/vlsmnid.jpg">
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/vlsmsub.jpg">
<br>
**CPT**
Setelah penghitungan IP di Tree, ip akan di assign ke masing masing pc atau router sesuai dengan subnetnya juga
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/cpt.png">
<br>
Kemudian pada setiap router dilakukan routing agar paket bisa sampai ke ip tujuan dan diberikan ip default 0.0.0.0/0 agar dari foosha bisa kembali ke asal
<br>
**WATER7**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Water7.png">
<br>
**FOOSHA**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Foosha.png">
<br>
**GUANHAO**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Guanhao.png">
<br>
**OIMO**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Oimo.png">
<br>
**PUCCI**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Pucci.png">
<br>
**ALABASTA**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Alabasta.png">
<br>
**SEASTONE**
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/Seastone.png">
<br>
Setelah routing dilakukan maka akan dicoba dengan Ping dari host ke tujuan dengan hasil sebagai berikut
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/run1.png">
<br>
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/VLSM/run2.png">
<br>

### 2. CIDR

**Diagram**

Pertama kami menentukan subnet yang ada dalam topologi dan melakukan `labelling` netmask terhadap masing-masing subnet dan didapatkan subnet A1 hingga A15

Lalu kami menggabungkan subnet paling luar (paling jauh dari internet) dari topologi tersebut. Contohnya adalah `A3 /25` dengan `A4 /21`menjadi `B1 /20` dan seterusnya. Hingga didapatkan hasil akhir subnet terbesar adalah `H1 /15`
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/CIDR/CIDR.png">

**Tree**

Karena subnet terbesar yang kami dapat adalah `H1 /15` maka IP root pada tree kami adalah `192.216.0.0/15`. Lalu root tersebut dibagi menjadi 2 yaitu `G1 /16` dengan IP `192.216.0.0 /16` `E1 /17` dengan IP `192.217.0.0/17`. Dengan menerapkan aturan pembagian IP tersebut, didapatlan susunan Tree kami sebagai berikut
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/CIDR/TreeModul4-CIDR.jpg">

**Tabel**

Menata hasil tree kedalam tabel

<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/CIDR/tabel.jpg">

**GNS3**

Pertama, membuat topologi sesuai permintaan soal dan menginputkan IP pada masing-masing router dan host sesuai pembagian pada tabel.

<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/CIDR/GNS3.png">

Melakukan routing pada masing-masing router dan host

**WATER7**

```
route add -net 192.217.0.128 netmask 255.255.255.128 gw 192.217.0.26 #JIPANGU
route add -net 192.217.0.0 netmask 255.255.248.0 gw 192.217.0.26 #COURTYARD CALMBELT
```

**FOOSHA**

```
route add -net 192.217.0.128 netmask 255.255.255.128 gw 192.217.0.22 #JIPANGU
route add -net 192.217.0.0 netmask 255.255.248.0 gw 192.217.0.22 #COURTYARD CALMBELT
route add -net 192.217.20.0 netmask 255.255.252.0 gw 192.217.0.22 #CIPHER
route add -net 192.216.12.0 netmask 255.255.252.0 gw 192.216.0.14 #JABRA
route add -net 192.216.8.0 netmask 255.255.254.0 gw 192.216.0.14 #MAINGATE
route add -net 192.216.0.48 netmask 255.255.255.240 gw 192.216.0.14 #JORGE
route add -net 192.216.0.4 netmask 255.255.255.252 gw 192.216.0.14 #FUKUROU
route add -net 192.216.1.0 netmask 255.255.255.0 gw 192.216.0.14 #ENIESLOBBY
```

**GUANHAO**

```
route add -net 192.216.0.48 netmask 255.255.255.240 gw 192.216.8.3 #JORGE
route add -net 192.216.0.4 netmask 255.255.255.252 gw 192.216.0.10 #FUKUROU
route add -net 192.216.1.0 netmask 255.255.255.0 gw 192.216.0.10 #ENIESLOBBY
```

**OIMO**

```
route add -net 192.216.0.0 netmask 255.255.252.0 gw 192.216.1.3 #ELENA
```

Menambahkan nameserver pada masing-masing router dan host

```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
```

**Dokumentasi Hasil**

<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/CIDR/calmbelt-jorge.png">
<img src="https://github.com/KevinNath01/Jarkom-Modul-4-T10-2021/blob/main/CIDR/jabra-google.png">
