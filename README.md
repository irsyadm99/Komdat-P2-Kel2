# Laporan Proyek Akhir KOM312 Komunikasi Data dan Jaringan
# ![](webapp/public/favicon-32x32.png)KOMGA
Original repository : https://github.com/gotson/komga
Web official : https://komga.org/

# Anggota
<table>
    <thead>
        <tr>
            <th></th>
            <th>Nama</th>
            <th>Nim</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Irsyad Musyaffa</td>
            <td>G64180048</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Rafi Solichin</td>
            <td>G64180068</td>
        </tr>
        <tr>
            <td>3</td>
            <td>M Fathan Fatazka</td>
            <td>G64180118</td>
        </tr>
        <tr>
            <td>3</td>
            <td>M Ihsan Fadillah WP</td>
            <td>G64180071</td>
        </tr>
</tbody>
</table>

---

# Deskripsi Aplikasi
Komga merupakan aplikasi server untuk komik dan manga, komga juga gratis dan open source.

Komga memiliki fitur antara lain :
- Browse libraries, series and books
- Search bar
- Download book files
- Manage multiple users, with per-library accesss control
- Webreader

Berikut adalah tipe file yang dapat dibaca oleh komga :
- Comic book archives: CBZ and CBR (except RAR5 and solid archives)
- Comic books in EPUB format
- PDF files

Komga juga dapat dijalankan pada semua sistem yang dapat menjalankan docker ataupun java :
- Windows
- macOS
- Linux
- Many popular NAS devices such as QNAP, Synology and more
---
Kami menginstall aplikasi pada VM lokal sistem operasi yang digunakan adalah Ubuntu 20.04.2.0 LTS

Ada dua metode untuk instalasi Komga :
- Menggunakan Docker
- Menggunakan java dengan jar file

Dalam hal ini kami menggunakan java
# Proses instalasi 
## 1. Java
Karena kami akan menggunakan java maka pastikan sudah memasang JRE/JDK pada mesin.
Pilihan termudah untuk menginstal Java adalah dengan menggunakan versi yang dikemas beserta Ubuntu. Secara asali, Ubuntu 20.04 meliputi Open JDK 11, yang merupakan varian sumber terbuka dari JRE dan JDK.

Untuk menginstal versi ini, perbarui indeks paket terlebih dahulu:
````
$ sudo apt update
````
Jalankan perintah berikut untuk menginstal Java Runtime Environment (JRE) asali yang akan menginstal JRE dari OpenJDK terbaru:
````
$ sudo apt install default-jre
````
atau bisa juga dengan perintah berikut:
````
$ sudo apt install default-jdk
````
## 2. Apache,MySQL,PHP(LAMP),Stack
Aplikasi akan dijalankan pada lokal dari mesin kita, untuk dapat menggunakan localhost maka diperlukan setup terhadap hal-hal tersebut.

Karena cukup detail maka silahkan kunjungi link berikut dan ikuti petunjuk yang ada pada artikel tersebut: https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-ubuntu-18-04

Jika sudah selesai, coba masuk ke localhost melalui web browser. Maka tampilan nya akan seperti berikut:
![](src/localhost.png)

## 3. Komga
Kita akan menjalankan komga menggunakan jar file, versi terbaru dari komga jar file dapat didownload melalui laman ini : https://github.com/gotson/komga/releases

pada laporan ini kami menggunakan komga v0.80.0, sebelum itu silahkan cek terlebih dahulu versi dari java yang ada pada mesin karena komga hanya dapat dijalankan pada
java version 8+ . Silahkan cek versi java dengan perintah ```` $ java --version ````
