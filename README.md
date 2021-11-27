# Jarkom-Modul-4-T10-2021

PRAKTIKUM MODUL 4 JARINGAN KOMPUTER 2021

Anggota Kelompok T10:<br>

1. Tri Rizki Yuliawan (05311940000024) <br>
2. Kevin Nathaniel (05311940000032) <br>
3. I Gde Ardha Semaranatha Gunasatwika (05311940000034) <br>

# Soal <a name="Soal"></a>

### 2. VLSM

### 2. CIDR

**Diagram**

**Tree**

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