<p align="center">
  <!--<b>Some Links:</b><br>
  //<a href="#">Link 1</a> |
  //<a href="#">Link 2</a> |
  //<a href="#">Link 3</a>
  //<br><br> -->
  <img src="https://user-images.githubusercontent.com/62282651/111072088-a425b080-850b-11eb-9393-ec330fba5ad6.png" width="400px" height="400px">
</p>

<h3 align="center"> KOMGA </h3>


<h1 align="center">Laporan Projek Akhir <br> Komunikasi Data dan Jaringan Komputer (KOM312) </h1>

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
            <td>M Ihsan Fadillah WP</td>
            <td>G64180071</td>
        </tr>
        <tr>
            <td>4</td>
            <td>M Fathan Fatazka</td>
            <td>G64180118</td>
        </tr>
</tbody>
</table>

---
[Deskripsi Aplikasi](#deskripsi-aplikasi) | [Proses Instalasi](#proses-instalasi) | [Port Forward](#port-forward-ke-windows) | [Kesimpulan](#kesimpulan) | [Referensi](#referensi) 
:-:|:-:|:-:|:-:|:-:


# Deskripsi Aplikasi
[`^ Kembali Ke Atas ^`](#) 

**Komga** merupakan aplikasi server untuk komik dan manga, **Komga** juga gratis dan open source.

**Komga** memiliki fitur antara lain :
- Browse libraries, series and books
- Search bar
- Download book files
- Manage multiple users, with per-library accesss control
- Webreader

Berikut adalah tipe file yang dapat dibaca oleh **Komga** :
- Comic book archives: CBZ and CBR (except RAR5 and solid archives)
- Comic books in EPUB format
- PDF files

**Komga** juga dapat dijalankan pada semua sistem yang dapat menjalankan Docker ataupun Java :
- Windows
- macOS
- Linux
- Many popular NAS devices such as QNAP, Synology and more
---
Kami menginstall aplikasi pada VM lokal sistem operasi yang digunakan adalah Ubuntu 20.04.2.0 LTS

Ada dua metode untuk instalasi **Komga** :
- Menggunakan Docker
- Menggunakan Java dengan jar file

Dalam hal ini kami menggunakan Java

# Proses instalasi
[`^^ Kembali Ke Atas ^^`](#)

## 1. Java
Karena kami akan menggunakan Java maka pastikan sudah memasang JRE/JDK pada mesin.
Pilihan termudah untuk menginstal Java adalah dengan menggunakan versi yang dikemas beserta Ubuntu. Secara asali, Ubuntu 20.04 meliputi Open JDK 11, yang merupakan varian sumber terbuka dari JRE dan JDK.

Untuk menginstal versi ini, perbaharui indeks paket terlebih dahulu:
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
## 2. Apache, MySQL, PHP (LAMP), dan Stack
Aplikasi akan dijalankan pada lokal dari mesin kita, untuk dapat menggunakan localhost maka diperlukan setup terhadap hal-hal tersebut.

Karena cukup detail maka silahkan kunjungi link berikut dan ikuti petunjuk yang ada pada artikel tersebut: https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-ubuntu-18-04

Jika sudah selesai, coba masuk ke localhost melalui web browser. Maka tampilan nya akan seperti berikut:
<br>
![](src/localhost.png)

## 3. Komga
Kita akan menjalankan **Komga** menggunakan jar file, versi terbaru dari **Komga** jar file dapat didownload melalui laman ini : https://github.com/gotson/komga/releases

Pada laporan ini kami menggunakan **Komga** v0.80.0, sebelum itu silahkan cek terlebih dahulu versi dari Java yang ada pada mesin karena **Komga** hanya dapat dijalankan pada
Java version 8+ . Silahkan cek versi Java dengan perintah ```` $ java --version ````

Lalu berikutnya jalankan perintah berikut untuk menjalankan **Komga**:
````
$ java -jar komga-0.80.0.jar 
````
Setelah **Komga** berhasil dijalankan, kita bisa mengakses web nya melalui : ```` http://<your-server>:<port>(/baseUrl) ````
karena pada laporan ini **Komga** dijalankan pada lokal maka `` <your-server> `` adalah `` localhost `` dan default `` <port> `` adalah 8080.

Berikut adalah tampilan awal ketika mengakses localhost:8080  :
<br>
![](src/login.png)
<br><br>
Silahkan melakukan pendaftaran akun dan login, Setelah itu akan diarahkan pada halaman home. 
<br>
![](src/home2.png)
<br>
Halaman home tersebut telah kami isi dengan komik/manga dan EPUB yang sebelumnya telah disiapkan. Perlu perhatikan bahwa **Komga** hanya dapat membaca tipe file tertentu, bisa di cek pada halaman awal laporan ini. Dengan ini menunjukan bahwa aplikasi web telah berhasil di instalasi pada server.

# Port Forward ke Windows
[`^^^ Kembali Ke Atas ^^^`](#)

Sekarang akan dilakukan port forward sehingga **Komga** dapat dijalankan diluar VM, dalam hal ini yaitu dijalankan pada Windows.

Sebelum itu pastikan telah menginstall open ssh pada Windows dan VM. VM yang kami gunakan adalah Ubuntu. Open ssh pada Windows biasanya sudah otomatis terinstall, sedangkan pada VM ubuntu perlu instalasi terlebih dahulu. Lakukan *command* ini secara bertahap:
````
$ sudo apt-get install openssh-server
$ sudo systemctl enable ssh
$ sudo systemctl start ssh

````
Setelah selesai instalasi ssh pada VM dan juga menjalankannya. Selanjutnya silahkan pergi ke CMD windows dan login ke ssh:
````
$ ssh user@server-name -p [port untuk ssh]
````
User dapat di cek pada terminal VM dengan command `` whoami `` dan ``server-name`` default nya adalah ``localhost``, kami menggunakan port 2200 untuk ssh

jangan lupa untuk melakukan setting pada virtual box manajer, masuk ke 'Settings -> Network -> Advance -> Port Forwarding', berikut juga beberapa aturan yang kami tambahkan :

Aturan *port forwarding*
Name   | Protocol   | Host IP    | Host Port  | Guest IP   | Guest Port
----   | --------   | -------    | ---------  | --------   | ----------
http   | TCP        |127.0.0.1   | 8000       |10.0.2.15   | 80
ssh    | TCP        |127.0.0.1   | 2200       |10.0.2.15   | 22
App    | TCP        |127.0.0.1   | 8080       |10.0.2.15   | 8080

Sekarang **Komga** sudah siap dijalankan dengan aturan App dan berjalan pada port 8080 di host dan juga port 8080 di guest.
<br>
![](src/win-home.PNG)
<br>

# Kesimpulan
[`^^^^ Kembali Ke Atas ^^^^`](#)

Pada kesempatan kali ini, kita sudah mencoba melakukan pemasangan aplikasi berbasis web pada server Ubuntu. Kami menggunakan server Ubuntu 20.04.2.0 LTS. Aplikasi web yang kami pilih adalah **Komga**, sebuah media server untuk menyimpan komik, manga, hingga majalah. **Komga** memiliki salah satu fitur berupa browse libraries, series and books. Dengan mendukung proses pembacaan file dengan format CBZ dan CBR (except RAR5 and solid archives) salah satunya. 

[Proses Instalasi](#proses-instalasi) dibagi menjadi tiga bagian meliputi Java; Apache, MySql, PHP (LAMP), dan Stack; serta terakhir aplikasi **Komga** itu sendiri. Kemudian untuk menambah kemudahan bagi pengguna, dilakukan [Port Forward ke Windows](#port-forward-ke-windows) agar aplikasi dapat diakses atau digunakan pada sistem operasi lain yang dalam hal ini adalah windows. Cukup sekian penyampaian projek mata kuliah Komunikasi Data dan Jaringan Komputer kelompok kami. Terima kasih ~

# Referensi

1. [How to Install Linux, Apache, MySql, PHP (LAMP), and Stack](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-ubuntu-18-04) - Digital Ocean
2. [Komga Source Code](https://github.com/gotson/komga) - Github
3. [Official Website](https://komga.org/) - Komga
4. [Install SSH On Ubuntu](https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/) - Cyber Citi
