# Jarkom-Modul-2-D07-2022

### Kelompok D07

| **No** | **Nama**                     | **NRP**    |
| ------ | -----------------------------| ---------- |
| 1      | Reza Maranello Alfiansyah    | 5025201071 |
| 2      | Nuzul Abatony                | 5025201107 |
| 3      | Muhammad Raihan Athallah     | 5025201206 |

## Nomor 1
WISE akan dijadikan sebagai DNS Master, Berlint akan dijadikan DNS Slave, dan Eden akan digunakan sebagai Web Server. Terdapat 2 Client yaitu SSS, dan Garden. Semua node terhubung pada router Ostania, sehingga dapat mengakses internet.

![image](https://user-images.githubusercontent.com/78489357/198051364-5befaf60-625b-453d-82bb-ea4ecd51defa.png)


Prefix IP [D07] : 192.188

Ostania
```
auto eth0
iface eth0 inet dhcp
auto eth1
iface eth1 inet static
	address 192.188.1.1
	netmask 255.255.255.0
auto eth2
iface eth2 inet static
	address 192.188.2.1
	netmask 255.255.255.0
auto eth3
iface eth3 inet static
	address 192.188.3.1
	netmask 255.255.255.0
```
SSS
```
auto eth0
iface eth0 inet static
	address 192.188.1.2
	netmask 255.255.255.0
	gateway 192.188.1.1
```
Garden
```
auto eth0
iface eth0 inet static
	address 192.188.1.3
	netmask 255.255.255.0
	gateway 192.188.1.1
```
Berlint
```
auto eth0
iface eth0 inet static
	address 192.188.2.2
	netmask 255.255.255.0
	gateway 192.188.2.1
```
Eden
```
auto eth0
iface eth0 inet static
	address 192.188.2.3
	netmask 255.255.255.0
	gateway 192.188.2.1
```
WISE
```
auto eth0
iface eth0 inet static
	address 192.188.3.2
	netmask 255.255.255.0
	gateway 192.188.3.1
```

<ol>
    <li> Buka console Ostania dan inputkan command <code>iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s [Prefix IP].0.0/16</code>
    <li> Copylah isi dari <code>/etc/resolv.conf</code> dengan menginputkan <code>cat /etc/resolv.conf</code> dan mengcopy 
    <li> Masukan hasil yang telah dicopy ke resolv.conf node-node lainnya dengan <code>echo [isi] > /etc/resolv.conf</code>
</ol>


### Kendala
<ol>
    <li> tiap mau install sesuatu melalui console selalu gagal 
    <li> GNS nya ada yang tidak bisa import kuuhaku-nya
</ol>
