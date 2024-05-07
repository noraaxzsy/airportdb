# airportdb

Step Create Table:
1. Buka XAMPP dan Start MySQL dan Apache
2. Buka DBEAVER dan lakukan New Database Connection (Ctrl+Shift+N) 
3. Pilih MariaDB dan klik Next
4. Kosongkan isian Database dan Password
5. Klik Finish
6. Buat New SQL Script
7. Lakukan run query menggunakan perintah pada file airport_ddl.sql (total: 14 table)
8. Setelah create table berhasil dibuat lakukan load data pada table 

Step Load Data:
1. Buka XAMPP dan Start MySQL dan Apache
2. Buka Command Prompt (cmd) pada windows
3. Arahkan directory ke folder bin pada XAMPP Anda (e.g. D:\XAMPP\mysql\bin)
4. Ketik perintah mysql -u root (Anda akan masuk ke MariaDB monitor)
5. Ketik perintah showdatabase;
6. Ketik perintah use airportdb;
7. Ketik perintah LOAD DATA INFILE '/tsv_file/nama_file.tsv' INTO TABLE nama_table FIELDS TERMINATED BY '\t'LINES TERMINATED BY '\n';
8. Lakukan Load Data sesuai dengan urutan table. Apabila table tersebut memiliki foreign key di table lain, maka lakukan load table referensi terlebih dahulu 
9. KHUSUS UNTUK LOAD DATA AIRLINES, sebelumnya terlebih dahulu lakukan perintah SET FOREIGN_KEY_CHECKS = 0; ALTER TABLE AIRLINE ADD FOREIGN KEY (base_airport) REFERENCES airport (airport_id); kemudian lakukan load file data tsv
10. Lakukan Load pada semua file data (estimasi waktu: 2 jam 15 mnt)


Referensi cara lain melakukan Load menggunakan Python (Hanya sekali run):
https://www.linkedin.com/pulse/uploading-airportdb-free-sample-database-from-mysql-local-timbal/ 
