# Praktikum 4

# Membuat tabel pegawai
```SQL
CREATE TABLE pegawai (
    id_pegawai VARCHAR(10) PRIMARY KEY,
    nama_depan VARCHAR(50),
    nama_belakang VARCHAR(50),
    email VARCHAR(100),
    telepon VARCHAR(15),
    tgl_kontrak DATE,
    id_job VARCHAR(10),
    gaji INT,
    tunjangan INT
);
```
## Isi Tabel Pegawai
```SQL
INSERT INTO pegawai (idpegawai, nama_depan, nama_belakang, email, telepon, tgl_kontrak, id_job, gaji, tunjangan) VALUES
('E001', 'Ferry', 'gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
('E002', 'aris', 'ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
('E003', 'faiz', 'ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
('E004', 'emna', 'bunton', 'enna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
('E005', 'mike', 'scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
('E006', 'lincoln', 'burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```
![Screenshot 2024-05-22 122535](https://github.com/Aaqilah22/Praktikum4/assets/148038188/cd23427c-7fcf-4812-bc4d-fc4517778d8f)

1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000!
```SQL
SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```
![Screenshot 2024-05-22 123731](https://github.com/Aaqilah22/Praktikum4/assets/148038188/6d9ce4c7-55f9-4609-8abf-3e554a38f75c)

2. Tampilkan pegawai yang tunjangan NULL!
```SQL
SELECT * FROM pegawai WHERE tunjangan IS NULL;
```
![Screenshot 2024-05-22 124004](https://github.com/Aaqilah22/Praktikum4/assets/148038188/cc993241-eab2-45da-815b-cfe80e03b57b)

3. Tampilkan pegawai yang tunjangan tidak NULL!
```SQL
SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;
```
![Screenshot 2024-05-22 123831](https://github.com/Aaqilah22/Praktikum4/assets/148038188/f9769232-43d7-4daa-b095-67d7ab51a4ec)

4. Tampilkan/hitung jumlah/baris tabel pegawai!
```SQL
SELECT COUNT(*) Jumlah_Baris FROM pegawai;
```
![Screenshot 2024-05-22 124658](https://github.com/Aaqilah22/Praktikum4/assets/148038188/482e9ecc-50cb-4b12-bc03-5b1d25b4dec1)

5. Tampilkan/hitung total gaji di tabel pegawai!
```SQL
SELECT SUM(gaji) AS Total_Gaji FROM pegawai;
```
![Screenshot 2024-05-22 124709](https://github.com/Aaqilah22/Praktikum4/assets/148038188/d27b32fd-74c1-403a-949c-f612b7ddff50)

6. Tampilkan/hitung rata-rata gaji pegawai!
```SQL
SELECT AVG(gaji) AS rerata FROM pegawai;
```
![Screenshot 2024-05-22 124721](https://github.com/Aaqilah22/Praktikum4/assets/148038188/61cfad43-375c-4d80-8fa2-0e0af7f19206)

7. Tampilkan gaji terkecil!
```SQL
SELECT MIN(gaji) AS Gaji_Terendah FROM pegawai;
```
![Screenshot 2024-05-22 130549](https://github.com/Aaqilah22/Praktikum4/assets/148038188/891e380b-0e05-4642-a753-b6c6adbd0b39)

8. Tampilkan gaji terbesar!
```SQL
SELECT MAX(gaji) AS Gaji_Tertinggi FROM pegawai;
```
![Screenshot 2024-05-22 130602](https://github.com/Aaqilah22/Praktikum4/assets/148038188/cc7869bf-9d45-40c9-b2cb-a6ba9868c632)

# Membuat Tabel Hewan
```SQL
CREATE TABLE pegawai (
    idpegawai VARCHAR(20) PRIMARY KEY ,
    nama_depan VARCHAR(20),
    nama_belakang VARCHAR(20),
    email VARCHAR(15),
    telepon VARCHAR(15),
    tgl_kontrak DATE,
    id_job VARCHAR(10),
    gaji INT,
    tunjangan INT
);
```
## Memasukan Data Ke Dalam Tabel
```SQL
INSERT INTO hewan (id, name, owner, species, sex) VALUES
('P1', 'Puffball', 'Diane', 'Hamster', 'f'),
('P2', 'Claws', 'Gwen', 'cat', 'm'),
('P3', 'Fluffy', 'Haro 1d', 'cat', 'f'),
('P4', 'Buffy', 'Haro 1d', 'dog', 'f'),
('P5', 'Fang', 'Benny', 'dog', 'm'),
('P6', 'Bowser', 'Diane', 'dog', 'm'),
('P7', 'Chirpy', 'Gwen', 'bird', 'f'),
('P8', 'Whistler', 'Gwen', 'bird', NULL),
('P9', 'Slim', 'Benny', 'snake', 'm');
```
![Screenshot 2024-05-22 133021](https://github.com/Aaqilah22/Praktikum4/assets/148038188/8d6c5275-00c7-4bf4-aedc-2bdefcbb2a92)

1. Tampilkan jumlah hewan yang dimiliki setiap owner
```SQL
SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY OWNER;
```
![Screenshot 2024-05-22 133036](https://github.com/Aaqilah22/Praktikum4/assets/148038188/2cebfbf1-4c41-477f-9384-263dcb5c110d)

2. Tampilkan jumlah hewan berdasarkan species
```SQL
SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;
```
![Screenshot 2024-05-22 133054](https://github.com/Aaqilah22/Praktikum4/assets/148038188/5b7133b5-8a6e-4c6c-bd7f-d8d7918b1d61)

3. Tampilkan jumlah hewan berdasarkan jenis kelamin
```SQL
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;
```
![Screenshot 2024-05-22 133107](https://github.com/Aaqilah22/Praktikum4/assets/148038188/3b838d60-1ea6-46e2-a38c-9d80f37039ef)

4. Tampilkan jumlah hewan berdasarkan species dan jenis kelamin
```SQL
SELECT  species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```
![Screenshot 2024-05-22 133121](https://github.com/Aaqilah22/Praktikum4/assets/148038188/6c717472-5441-4e8a-aef2-faac24295bf5)

5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin
```SQL
SELECT species, sex COUNT(*) AS jumlah_hewan FROM hewan WHERE species IN('cat', 'dog') GROUP BY species, sex;
```
![Screenshot 2024-05-22 133210](https://github.com/Aaqilah22/Praktikum4/assets/148038188/4cc6c9e1-ab66-4b74-a821-b02f3eb36cb3)

6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja
```SQL
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```
![Screenshot 2024-05-22 133222](https://github.com/Aaqilah22/Praktikum4/assets/148038188/2715ec6b-8233-4b57-a671-37c931043264)

## KESIMPULAN 
1. Operator IN dan IS NULL: Operator IN digunakan untuk memfilter data yang terdapat dalam list tertentu. Operator IS NULL digunakan untuk menampilkan data dengan nilai NULL atau IS NOT NULL untuk menampilkan data yang bukan NULL.
2. Fungsi Agregat (COUNT, SUM, AVG, MIN, MAX) digunakan untuk melakukan perhitungan pada kolom. COUNT digunakan untuk menghitung jumlah baris, SUM digunakan untuk menjumlahkan nilai kolom, AVG digunakan untuk menghitung rata-rata, MIN digunakan untuk menampilkan nilai terkecil, dan MAX digunakan untuk menampilkan nilai terbesar.
3. Klausa GROUP BY digunakan untuk mengelompokkan data berdasarkan satu atau beberapa kolom, GROUP BY memungkinkan menggunakan fungsi agregat.
