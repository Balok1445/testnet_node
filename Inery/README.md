<p style="font-size:14px" align="right">
<a href="https://t.me/BeritaCryptoo" target="_blank">Join our telegram <img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
<a href="https://twitter.com/BeritaCryptoo" target="_blank">Join our twitter <img src="https://user-images.githubusercontent.com/108946833/184274157-08210464-fa03-493d-b01c-2420c67a524f.jpg" width="30"/></a>
</p>
 
<p align="center">
  <img height="50" height="auto" src="https://user-images.githubusercontent.com/38981255/184088981-3f7376ae-7039-4915-98f5-16c3637ccea3.PNG">
</p>

# Tutorial Become a Master Node

## Perangkat Keras

|  Komponen |  Persyaratan Minimum |
| ------------ | ------------ |
| CPU  | Intel Core i7-8700 Hexa-Core  |
| RAM | DDR4 64 GB  |
| Penyimpanan  | 2x1 TB NVMe SSD |
| koneksi | Port 1 Gbit/dtk |

|  Komponen |  Persyaratan Minimum |
| ------------ | ------------ |
| CPU  | Intel Core i3 or i5 |
| RAM | 4 GB DDR4 RAM |
| Penyimpanan  | 500 GB HDD|
| koneksi | 100 Mbit/s port |

## Perangkat Lunak

|Komponen | Persyaratan Minimum |
| ------------ | ------------ |
| OS | Ubuntu 20.04 atau lebih tinggi | 

## Sebelum Menjalankan Node Register Akun Testnet
>- [Register](https://testnet.inery.io/)

Dokumen Official :
> [Node Lite & Master](https://docs.inery.io/docs/category/lite--master-nodes)

Explorer :
> [Explorer Inary](https://explorer.inery.io/ "Explorer Inary")

## Open Port
```
ufw allow 22 && ufw allow ssh && ufw allow 8888 && ufw allow 9010 && ufw enable
```

## Mengisntall Dependencies
```
sudo apt-get update && sudo apt install git && sudo apt install screen 
```
```
sudo apt-get install -y make bzip2 automake libbz2-dev libssl-dev doxygen graphviz libgmp3-dev \
autotools-dev libicu-dev python2.7 python2.7-dev python3 python3-dev \
autoconf libtool curl zlib1g-dev sudo ruby libusb-1.0-0-dev \
libcurl4-gnutls-dev pkg-config patch llvm-7-dev clang-7 vim-common jq libncurses5
```
## Install Node
- Unduh paket Inery Node
```
git clone  https://github.com/inery-blockchain/inery-node
```

## Explorer BIN
```
cd inery-node
```
## Beri Izin File

```
cd inery.setup
```
```
chmod +x ine.py
```
```
./ine.py --export
```
```
cd; source .bashrc; cd -
```
<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/108946833/194111185-74b2ea9d-d3db-4b5f-879e-eabc4eb1aa63.png">
</p>

## Konfigurasi Master Node

```
cd tools
```
```
nano config.json
```
temukan "MASTER_ACCOUNT" dan ganti placeholder IP = IP atau alamat DNS server
```
"MASTER_ACCOUNT":
"NAME": "AccountName",
"PUBLIC_KEY": "PublicKey",
"PRIVATE_KEY": "PrivateKey",
"PEER_ADDRESS": "IP:9010",
"HTTP_ADDRESS": "0.0.0.0:8888",
"HOST_ADDRESS": "0.0.0.0:9010"
```
Kemudian ganti account name, publickey, privatekey, ip (sesuai kan dengan yang ada di web testnetnya)

**Simpan (ctrl+S), Ketik "Y" dan keluar (ctrl+X)**

Jika kalian menggunakan [mobaxterm](https://mobaxterm.mobatek.net/download.html) bisa cari folder `/root/inery-node/inery.setup/tools/config.json`, Lalu simpan yang sudah di edit.
## Running Node
```
cd inery.setup
```
```
screen -S inery
```
```
./ine.py --master
```
<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/108946833/194216311-9c4238d2-3a6a-4aaf-ab39-cb4eeb9c4265.png">
</p>

**Ketik CTRL + A + D** Untuk jalan di Background dan Untuk Kembali lagi Ke Screen Gunakan Perintah `screen -rd inery`

## Jika ada error maka kalian harus mengganti peers
Kalau muncul error nya ada 2, itu masih normal, bisa lanjut ke next step.
```
cd inery-node/inery.setup/master.node/
nano genesis_start.sh
```
## Add Peer baru
<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184370626-5b3dc227-3800-4140-a9c0-ce5b0b13e1e1.PNG">
</p>

**Isi Seperti Pada Contoh Gambar**

- 62.210.245.223
- 192.99.62.6
- 15.235.133.9

## Masukan Peer
```
--p2p-peer-address 167.235.3.147:9010 \
--p2p-peer-address 135.181.133.169:9010 \
--p2p-peer-address 15.235.133.9:9010 \
--p2p-peer-address 38.242.229.50:9010 \
--p2p-peer-address sys.blockchain-servers.world:9010 \
--p2p-peer-address bis.blockchain-servers.world:9010 \
--p2p-peer-address 167.235.71.28:9010 \
--p2p-peer-address 62.210.245.223:9010 \
--p2p-peer-address 192.99.62.6:9010 \
--p2p-peer-address 15.235.133.9:9010 \
--p2p-peer-address 5.161.96.50:9010 \
--p2p-peer-address 15.235.133.9:9010 \
```
**Save CTRL X lalu Y dan Enter**

**Penting :** Peer di Atas, Jika Sudah Tidak Work Kalian Bisa Cari Peer Baru di Discord Inery.

## Restart Node
```
./stop.sh
```

Tunggu Sekitar 5-10 Detik

```
./genesis_start.sh
```

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/108946833/194226595-bdc1a188-48c2-42d8-bbeb-363458ff5263.png">
</p>

Jika Sudah Seperti Gambar di Atas, Artinya Sudah jalan dan Tunggu Sampai 8 Jam Untuk Mensinkronkan (Ngejar Block Yang Ada di Explorer)

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/108946833/194457432-25143e6f-5384-40e4-b1f6-40cbc1f9736e.png">
</p>


Jika Sudah Seperti gambar di atas, Arti nya Sudah Selesai Sinkron, Silahkan Lanjut Next Step

## Start Node
### Lakukan Ini Masih di TAB Baru
```
cd ~/inery-node/inery.setup/master.node/
./start.sh
```
## Daftar dan setujui (Menghubungkan Wallet dengan Dasboard Akun)

### Lakukan Ini Masih di TAB Baru

```
cline wallet create -n <your_name_wallet> -f file.txt
```
file.txt berisi Password Wallet kalian (Kalian membutuhkan itu Jika Wallet kalian dalam Keadaan Lock)
```
cline wallet import --private-key <your_private_key> -n <your_name_wallet>
```
Import Private Key kalian ke Wallet

### Daftar sebagai produser dengan menjalankan perintah:

```
cline system regproducer <your_account> <your_public_key> 0.0.0.0:9010
```
```
cline system makeprod approve <your_account> <your_account>
```
Semua Perintah di atas Jalankan tanpa tanda (<>)

**Note :** Silahkan Check di Explorer Inery.

## Jika wallet kalian ke lock gunakan cara ini
<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/108946833/194457095-1b3b24c2-102d-4381-827d-629975b4e71d.png">
</p>

```
cline wallet unlock -n namawallet
```

Untuk Melihat password
```
cat file.txt
```


# Perintah Berguna 

## Check Saldo Wallet 
```
cline get currency balance inery.token ACCOUNT_NAME
```
## Delete Wallet di Node
```
cline wallet stop
```
```
rm -rf inery-wallet
rm -rf file.txt
rm -rf defaultWallet.txt
```
