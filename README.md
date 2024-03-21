# 3.3.12-Packet-Tracer-VLAN-Configuration-T-UAS-
#### Simulasi "Packet Tracer - Konfigurasi VLAN" merupakan latihan praktis yang dirancang untuk memperkenalkan konsep dan implementasi Virtual Local Area Network (VLAN) dalam sebuah jaringan komputer.
![image](https://github.com/firmansultoni/3.3.12-Packet-Tracer-VLAN-Configuration-T-UAS-/assets/113542409/1f82c371-4120-4ee6-b2f5-c8f319a0f99a)
# 
## Addressing Table
![image](https://github.com/firmansultoni/3.3.12-Packet-Tracer-VLAN-Configuration-T-UAS-/assets/113542409/e1706f7a-164b-42fb-a10d-daff7672f74b)
## 
## Objectives
#### > Bagian 1: Verifikasi Konfigurasi VLAN Default
#### > Bagian 2: Konfigurasikan VLAN
#### > Bagian 3: Tetapkan VLAN ke Port
## Background
#### VLAN berguna dalam administrasi grup logis, memungkinkan anggota grup dengan mudah dipindahkan, diubah, atau ditambahkan. Kegiatan ini berfokus pada pembuatan dan penamaan VLAN, serta penetapan port akses ke VLAN tertentu.

# Bagian 1: Lihat Konfigurasi VLAN Default
## Langkah 1: Tampilkan VLAN saat ini.
#### Di S1, keluarkan perintah yang menampilkan semua VLAN yang dikonfigurasi. Secara default, semua antarmuka ditetapkan ke VLAN 1.
### tampilkan gambar S1#tampilkan vlan singkat di sini 

## Langkah 2: Verifikasi konektivitas antar PC di jaringan yang sama.
#### Perhatikan bahwa setiap PC dapat melakukan ping ke PC lain yang berbagi subnet yang sama.
#### > PC1 dapat melakukan ping ke PC4
#### > PC2 dapat melakukan ping ke PC5
#### > PC3 dapat melakukan ping ke PC6
#### Ping ke host di jaringan lain gagal.
#### Manfaat apa yang dapat diberikan VLAN pada jaringan?
#### `Manfaat utama menggunakan VLAN adalah sebagai berikut: keamanan, pengurangan biaya, kinerja lebih tinggi, mitigasi badai siaran, peningkatan efisiensi staf TI, dan manajemen proyek dan aplikasi yang lebih sederhana.`

# Bagian 2: Konfigurasikan VLAN
## Langkah 1: Buat dan beri nama VLAN di S1.
#### A. Buat VLAN berikut. Nama peka huruf besar-kecil dan harus sama persis dengan persyaratan:

#### • VLAN 10: Fakultas/Staf

##### `S1#(config)# vlan 10`
##### `S1#(config-vlan)# name Faculty/Staff`

#### B. Buat VLAN yang tersisa.
#### • VLAN 20: Students
#### • VLAN 30: Guest(Default)
#### • VLAN 99: Management&Native
#### • VLAN 150: VOICE

##### `S1(config-vlan)#vlan 20`
##### `S1(config-vlan)#name Students`
##### `S1(config-vlan)#vlan 30`
##### `S1(config-vlan)#name Guest(Default)`
##### `S1(config-vlan)#vlan 99`
##### `S1(config-vlan)#name Management&Native`
##### `S1(config-vlan)#vlan 150`
##### `S1(config-vlan)#name VOICE`

## Langkah 2: Verifikasi konfigurasi VLAN.
#### Perintah mana yang hanya akan menampilkan nama VLAN, status, dan port terkait pada sebuah switch?

##### S1#tampilkan gambar vlan singkat#tampilkan vlan singkat di sini

## Langkah 3: Buat VLAN di S2 dan S3.
##### Gunakan perintah yang sama dari Langkah 1 untuk membuat dan memberi nama VLAN yang sama pada S2 dan S3.

#### S2
##### `S2(config)#vlan 10`
##### `S2(config-vlan)#name Faculty/Staff`
##### `S2(config-vlan)#vlan 20`
##### `S2(config-vlan)#name Students`
##### `S2(config-vlan)#vlan 30`
##### `S2(config-vlan)#name Guest(Default)`
##### `S2(config-vlan)#vlan 99`
##### `S2(config-vlan)#name Management&Native`
##### `S2(config-vlan)#vlan 150`
##### `2(config-vlan)#name VOICE`

#### S3
##### `S3(config)#vlan 10`
##### `S3(config-vlan)#name Faculty/Staff`
##### `S3(config-vlan)#vlan 20`
##### `S3(config-vlan)#name Students`
##### `S3(config-vlan)#vlan 30`
##### `S3(config-vlan)#name Guest(Default)`
##### `S3(config-vlan)#vlan 99`
##### `S3(config-vlan)#name Management&Native`
##### `S3(config-vlan)#vlan 150`
##### `S3(config-vlan)#name VOICE`

## Langkah 4: Verifikasi konfigurasi VLAN.
##### `show vlan brief`

# Bagian 3: Tetapkan VLAN ke Port
## Langkah 1: Tetapkan VLAN ke port aktif di S2.

#### A. Konfigurasikan antarmuka sebagai port akses dan tetapkan VLAN sebagai berikut:
#### > VLAN 10: FastEthernet 0/11
##### `S2(config)# interface f0/11`
##### `S2(config-if)# switchport mode access`
##### `S2(config-if)# switchport access vlan 10`

#### B. Tetapkan port yang tersisa ke VLAN yang sesuai.
#### > VLAN 20: FastEthernet 0/18
#### > VLAN 30: FastEthernet 0/6

##### `S2(config-if)#interface f0/18`
##### `S2(config-if)#switchport mode access`
##### `S2(config-if)#switchport access vlan 20`
##### .
##### `S2(config-if)#interface f0/6`
##### `S2(config-if)#switchport mode access`
##### `S2(config-if)#switchport access vlan 30`
##### `S2(config-if)#`

## Langkah 2: Tetapkan VLAN ke port aktif di S3.
#### S3 menggunakan penetapan port akses VLAN yang sama dengan S2. Konfigurasikan antarmuka sebagai port akses dan tetapkan VLAN sebagai berikut:
#### • VLAN 10: FastEthernet 0/11
#### • VLAN 20: FastEthernet 0/18
#### • VLAN 30: FastEthernet 0/6

##### `S3(config)#interface f0/11`
##### `S3(config-if)#switchport mode access`
##### `S3(config-if)#switchport access vlan 10`
##### .
##### `S3(config-if)#interface f0/18`
##### `S3(config-if)#switchport mode access`
##### `S3(config-if)#switchport access vlan 20`
##### .
##### `S3(config-if)#interface f0/6`
##### `S3(config-if)#switchport mode access`
##### `S3(config-if)#switchport access vlan 30`

## Langkah 3: Tetapkan VOICE VLAN ke FastEthernet 0/11 di S3.
#### Seperti yang ditunjukkan dalam topologi, antarmuka S3 FastEthernet 0/11 terhubung ke Cisco IP Phone dan PC4. Telepon IP berisi saklar tiga port 10/100 terintegrasi. Satu port di ponsel diberi label Switch dan terhubung ke F0/4. Port lain di ponsel diberi label PC dan terhubung ke PC4. Telepon IP juga memiliki port internal yang menghubungkan ke fungsi telepon IP.
#### .
#### Antarmuka S3 F0/11 harus dikonfigurasi untuk mendukung lalu lintas pengguna ke PC4 menggunakan VLAN 10 dan lalu lintas suara ke telepon IP menggunakan VLAN 150. Antarmuka juga harus mengaktifkan QoS dan mempercayai nilai Class of Service (CoS) yang ditetapkan oleh telepon IP . Lalu lintas suara IP memerlukan jumlah throughput minimum untuk mendukung kualitas komunikasi suara yang dapat diterima. Perintah ini membantu switchport untuk menyediakan jumlah throughput minimum ini.
##### `S3(config)# interface f0/11`
##### `S3(config-if)# mls qos trust cos`
##### `S3(config-if)# switchport voice vlan 150`

## Langkah 4: Verifikasi hilangnya konektivitas.
#### S2# tampilkan vlan singkat # tampilkan gambarnya disisni 

#### Coba ping antara PC1 dan PC4.

#### Meskipun port akses ditetapkan ke VLAN yang sesuai, apakah ping berhasil? jelaskan.
#### Jawab 
##### `Tidak, ping gagal karena port antar switch berada di VLAN 1 dan PC1 dan PC4 berada di VLAN 10.`
#### Apa yang dapat dilakukan untuk mengatasi masalah ini?
#### Jawab 
##### `Konfigurasikan port antar switch sebagai port trunk.`

# Kode Untuk Switch
## Switch S1
##### `vlan 10`
##### ` name Faculty/Staff`
##### `vlan 20`
##### ` name Students`
##### `vlan 30`
##### ` name Guest(Default)`
##### `vlan 99`
##### ` name Management&Native`
##### `vlan 150`
##### ` name VOICE`

## Switch S2
##### `vlan 10`
##### ` name Faculty/Staff`
##### `vlan 20`
##### ` name Students`
##### `vlan 30`
##### ` name Guest(Default)`
##### `vlan 99`
##### ` name Management&Native`
##### `vlan 150`
##### ` name VOICE`
##### `interface fa0/11`
##### ` switchport mode access`
##### ` switchport access vlan 10`
##### `interface fa0/18`
##### ` switchport mode access`
##### ` switchport access vlan 20`
##### `interface fa0/6`
##### ` switchport mode access`
##### ` switchport access vlan 30`

## Switch S3
##### `vlan 10`
##### ` name Faculty/Staff`
##### `vlan 20`
##### ` name Students`
##### `vlan 30`
##### ` name Guest(Default)`
##### `vlan 99`
##### ` name Management&Native`
##### `vlan 150`
##### ` name VOICE`
##### `interface fa0/11`
##### ` switchport mode access`
##### ` switchport access vlan 10`
##### ` mls qos trust cos`
##### ` switchport voice vlan 150`
##### `interface fa0/18`
##### ` switchport mode access`
##### ` switchport access vlan 20`
##### `interface fa0/6`
##### ` switchport mode access`
##### ` switchport access vlan 30`



