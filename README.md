# manajemen-basisdata-2

# Membuat databse management_hotel dan melakukan aksi
## 1. Membuat database

### Membuat Database
```
CREATE DATABASE management_hotel
```
### Membuat table kamar
```
CREATE TABLE `kamar` (
  `id_kamar` int(11) NOT NULL,
  `nomor_kamar` varchar(10) NOT NULL,
  `tipe_kamar` varchar(50) DEFAULT NULL,
  `harga_per_malam` decimal(10,2) DEFAULT NULL,
  `status` varchar(20) DEFAULT 'tersedia'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```
### Membuat table pelanggan
```
CREATE TABLE `pelanggan` (
  `id_pelanggan` int(11) NOT NULL,
  `nama` varchar(100) NOT NULL,
  `alamat` varchar(255) DEFAULT NULL,
  `no_telepon` varchar(20) DEFAULT NULL,
  `email` varchar(100) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```
### Membuat table pembayaran
```
CREATE TABLE `pembayaran` (
  `id_pembayaran` int(11) NOT NULL,
  `id_reservasi` int(11) DEFAULT NULL,
  `tanggal_pembayaran` date DEFAULT NULL,
  `jumlah` decimal(10,2) DEFAULT NULL,
  `metode_pembayaran` varchar(50) DEFAULT NULL,
  `status_pembayaran` varchar(20) DEFAULT 'pending'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```
### Membuat table reservasi
```
CREATE TABLE `reservasi` (
  `id_reservasi` int(11) NOT NULL,
  `id_pelanggan` int(11) DEFAULT NULL,
  `id_kamar` int(11) DEFAULT NULL,
  `tanggal_checkin` date DEFAULT NULL,
  `tanggal_checkout` date DEFAULT NULL,
  `total_harga` decimal(10,2) DEFAULT NULL,
  `status_reservasi` varchar(50) DEFAULT 'dipesan'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

## 2. Melakukan aksi terhadap database
