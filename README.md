# Sistem RFID Equipment

## Tujuan
* 1.	Mengidentifikasi semua equipment dan melakukan tagging RFID untuk setiap equipment 
* 2.	Mencatat perpindahan equipment
* 3.	Memudahkan untuk melakukan equipment opname (cek fisik equipment)
* 4.	Memudahkan untuk mencari equipment serta dibandingkan equipment yang terdaftar di SAP

## Fungsi-fungsi
* 1.	Proses tagging equipment dan update ke SAP
* 2.	Mendaftarkan lokasi sesuai lokasi equipment (functional location) di SAP
* 3.	Proses equipment opname per lokasi
* 4.	Proses equipment opname menggunakan mobile RFID reader
    * a.	Equipment opname akan dilakukan per lokasi
    * b.	User akan scan tag lokasi yang akan dilakukan equipment opname
    * c.	User berkeliling lokasi untuk membaca semua tag RFID 
    * d.	Jika selesai, maka akan terbentuk satu data set equipment opname, yang bisa disimpan dalam bentuk text file atau ke          database
* 5.	Proses perbandingan hasil equipment opname dengan master equipment di Server RFID
    * a.	Download master equipment SAP ke Server RFID
    * b.	Data equipment opname akan ditransfer ke Server RFID untuk dilakukan proses perbandingan 
    * c.	Kemungkinan hasil perbandingan untuk setiap equipment opname proses fixing data
        * i.	Tag hasil opname match dengan tag di SAP (Lokasi dan tag ID)
            * Tidak perlu dilakukan apapun
        * ii.	Tag ada di hasil opname, tag ada di SAP, tetapi lokasi SAP tidak sama
            * Lokasi SAP diperbaiki sesuai hasil equipment opname
        * iii.	Tag tidak ada di hasil opname, tetapi terdaftar di SAP
            * Cek ulang di lapangan apakah equipment terkait masih ada
            * Jika masih ada, maka perlu tag ulang
        * iv.	Tag ada di hasil opname, tag di SAP tidak ditemukan (tidak ada yang memakai)
            * Tag tidak berlaku lagi
            * Tag bisa dipakai ulang

* 6.	Proses update data ke Server RFID
        * i.	Proses ini dilakukan untuk menandakan kapan terakhir proses equipment opname dilakukan 
        * ii.	Data yang diupdate ke master equipment
            * Tanggal equipment opname
            * User yang melakukan equipment opname
            * Lokasi terakhir equipment
            * Tanggal & jam update
            * User yang update
