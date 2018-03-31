# Sekilas Tentang Joomla!

_**Joomla!**_ Joomla! adalah Sistem manajemen konten (SMK atau CMS) yang bebas dan terbuka (free opensource) ditulis menggunakan PHP dan basisdata MySQL untuk keperluan di internet maupun intranet. Joomla pertama kali dirilis dengan versi 1.0.0. Fitur-fitur Joomla! diantaranya adalah sistem caching untuk peningkatan performansi, RSS, blogs, poling, dll. Joomla! menggunakan lisensi GPL.

# Fitur yang tersedia
-	Blog with comments and RSS feeds
-   Polling
-   Images/Files uploading and sharing
-   System catching

# Instalasi

**Kebutuhan Sistem**

-   `PHP > 5.5`
-   `MySQL`
-   `Apache`

**Proses Instalasi :**

- Sebelum melakukan instalasi, atur port yang diperlukan, dengan cara :
    'Settings -> Network -> Advanced -> Port Forwarding'
-------------------------------------------------------------------------
    Name	Protocol    Host IP	    Host Port	Guest IP	Guest Port
-------------------------------------------------------------------------    
    http	TCP		                    8888		            80          
    ssh     TCP		                    2222		            22
-------------------------------------------------------------------------
-   _Update_ sistem dengan versi yang terbaru 
    `$ sudo apt-get update -y`
    
-   _Install_ ssh `$ sudo apt update` lalu
    `$ sudo apt install ssh`
    
-   _Install_ apache, MySQL, dan PHP, lalu restart system
```
$ sudo apt install apache2
$ sudo apt install mysql-server
$ sudo apt install php
$ sudo apt install libapache2-mod-php
$ sudo apt install php-mysql
$ sudo apt install php-gd php-mcrypt php-mbstring php-xml php-ssh2
$ sudo service apache2 restart
```
- Unduh versi terakhir dari Joomla! dengan cara <br>
`$ sudo wget https://downloads.joomla.org/cms/joomla3/3-8-6/Joomla_3-8-6-Stable-Full_Package.zip?format=zip`
- Untuk mempermudah, kita dapat meletakkannya di direktori Joomla! yang terdapat di dalam direktori html. Maka kita masuk ke dalam direktori html terlebih dahulu <br>
`$ cd /var/www/html/`
lalu membuat direktori Joomla! <br>
`$ sudo mkdir joomla`
- Masuk ke direktori Joomla yang telah kita buat <br>
`$ cd joomla`
- Selanjutnya kita ekstrak file yang telah diunduh dan meletakkannya di dalam direktori joomla <br>
`sudo unzip Joomla_3-8-6-Stable-Full_Package.zip?format=zip -d      /var/www/html/joomla`
- Selanjutnya kita atur kepemilikan direktori <br>
`$ sudo chown -R www-data:www-data /var/www/html/joomla/`
- Lalu atur perizinan akses direktori <br>
`$ sudo chmod 755 /var/www/html/joomla`
- Setelah itu kita restart apache dan mysql <br>
`$ systemctl restart apache2` <br>
`$ systemctl restart mysql.service`
- Selanjutnya kita akan menghilangkan direktori installation yang berada di dalam direktori joomla <br>
`$ cd /var/www/html/joomla/` untuk masuk ke direktori jumlah <br>
`$ sudo rm -rf installation/` untuk remove direktori
- Sekarang kita akan membuat database untuk sistem <br>
```mysql -u root -p
create database joomladb;
create user joomla identified by 'password';
grant all privileges on joomladb.* to joomla;
exit```

## Cara Pemakaian

Saat instalasi berhasil, tampilan yang akan muncul adalah seperti gambar berikut : <br>
<img src=https://raw.githubusercontent.com/jojowvan/joomla/master/12.JPG></img>

Setelah anda login, tampilan berubah menjadi sebagai berikut: <br>
<img src=https://raw.githubusercontent.com/jojowvan/joomla/master/13.JPG></img>

Untuk membuat kiriman baru, anda dapat memilih menu create a post yang berada pada kiri atas layar anda, seperti gambar berikut: <br>
<img src=https://raw.githubusercontent.com/jojowvan/joomla/master/1.JPG></img>

Jika anda telah membuat kiriman, maka kiriman tersebut akan tampil pada layar utama anda, seperti berikut: <br>
<img src=https://github.com/jojowvan/joomla/blob/master/2.JPG></img>

## Pembahasan
**Kelebihan**

-   Instalasi mudah
-   Merupakan salah satu open source CMS dengan fitur yang powerfull
-   Mudah dalam penggunaan
-   Dapat digunakan secar gratis dan hanya membayar web hosting
-   Komponen dan modul yang bisa kita dapat secara gratis

**Kekurangan**

-   Fasilitas multisite tidak tersedia pada joomla
-   Kurangnya cache memory yang disediakan
-   Keterbatasan sebuah ACL (access control list)

## Perbandingan dengan Blogging Platform lain (Wordpress vs Joomla!)
WordPress merupakan salah satu CMS sama seperti Joomla!, Wordpress secara spesifik ditujukan untuk membuat dan mengelola blog. Wordpress hadir dengan banyak pilihan template dan plugins. Berbeda dengan Wordpress, Joomla! hadir dengan user interface yang cukup sederhana dan dukungan desain dan template yang dapat kita ubah sesuai kebutuhan. Kedua CMS di atas memiliki keunggulan masing - masing baik di sistem maupun user interface, untuk popularitas Wordpress lebih unggul dibanding Joomla!. Namun Joomla! dapat dikatakan memilki kinerja yang powerful. 

## Referensi

1.  [Joomla!](http://joomlacode.org/gf/project/joomla/scmsvn/) \- Website resmi Joomla
2.  [Dewaweb](https://www.dewaweb.com/blog/inilah-perbandingan-cms-wordpress-drupal-dan-joomla/) \- Perbandingan Wordpress dan Joomla!
3.  [Command in ubuntu](https://www.hostinger.co.id/tutorial/pengertian-chmod-dan-chown-untuk-ganti-permission-di-linux/) \- Ubuntu Help
4.  [What is WordPress](https://en.wikipedia.org/wiki/WordPress) \- Wordpress
