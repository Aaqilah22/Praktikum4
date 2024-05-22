# Praktikum 4
# MEMBUAT TABEL PEGAWAI

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
