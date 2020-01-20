
# Command Line Interface (CLI)
Sub-Materi
1. [Basic Command](#1-basic-command)
2. [Administrative Command](#2-administrative-command)
3. [File Editing](#3-file-editing)
4. [Export Variable](#4-export-variable)
5. [Cek IP dan Koneksi](#5-cek-ip-dan-koneksi)
6. [Menginstall Software](#6-menginstall-software)

### 1. Basic Command
##### 1. pwd
*print working directory*. Untuk mengetahui di directory mana kita berada sekarang.
![pwd](img/pwd.png)

##### 2. ls
*list*. Untuk menampilkan file-file apa saja yang ada di suatu directory.
![ls](img/ls.png)  
Parameter yang sering dipakai pada perintah ls adalah `-a` dan `-l`.
- Saat menggunakan parameter `-a` maka semua file akan ditampikan, termasuk yang *hidden* (diawali dengan `.`).
![ls -a](img/ls_a.png)
- Sedangkan parameter `-l` menampilkan file yang tidak *hidden* dalam format *long-list*.
![ls -l](img/ls_l.png)

##### 3. man
*manuals*. Digunakan untuk melihat fungsi dan parameter dari suatu comman
Contoh `man ls` akan menampilkan manual penggunaan command `ls`.
Untuk keluar dari tampilan manual tersebut kita tinggal menekan tombol `q`.
![man](img/manls.png)

##### 4. cd
*change directory*. Digunakan untuk pindah ke directory lain. Syntax-nya adalah ```cd [namadirectory]```.
Misalnya kita sedang berada di directory `/home/Penunggu` dan ingin berpindah ke directory `Desktop/`. Maka command yang kita gunakan adalah `cd Desktop/`  
![cd](img/cd.png)  
Contoh lain:
+ `cd` atau `cd ~` untuk pindah ke directory home user
+ `cd /` untuk pindah ke directory root
+ `cd ..` untuk pindah ke parent directory dari directory sekarang
+ `cd -` untuk pindah ke working directory sebelumnya 
 
##### 5. mkdir
*make directory*. Digunakan untuk membuat sebuah directory (folder).
Syntax-nya adalah ```mkdir [namadirectory]```
![mkdir](img/mkdir.png)

##### 6. cp
*copy*. Digunakan untuk menyalin (meng-copy) file.
Syntax-nya adalah ```cp [namafile] [namacopyannya]```
![cp](img/cp.png)

##### 7. mv
*Move* Digunakan untuk memindahkan suatu file ke directory lain.
+ Untuk memindahkan file, syntax-nya adalah ```mv [namafile] [pathbarunya]```
![mv](img/mv.png)
+ Selain itu `mv` dapat juga digunakan untuk me-rename file, syntax-nya adalah ```mv [namafile] [namabaru]```
![mv](img/mv2.png)

##### 8. cat
*concatenate*. Digunakan untuk menampilkan isi dari suatu file.
![cat](img/cat.png)

##### 9. rm
*remove*. Digunakan untuk menghapus suatu file. Syntax-nya adalah ```rm [namafile]```
![rm](img/rm.png)  
Selain itu rm juga dapat digunakan untuk menghapus directory, yaitu dengan menambahkan parameter `-r`
![rm -r](img/rm_r.png)

##### 10. rmdir
*remove directory*. Digunakan untuk menghapus directory yang kosong. Syntax-nya adalah ```rmdir [namafolder]```
![rmdir](img/rmdir.png)

##### 11. echo
Digunakan untuk menampilkan string yang kita inputkan. Syntax-nya adalah ```echo [string yang diinginkan]```
![echo](img/echo.png)

##### 12. grep
Digunakan untuk menampilkan setiap baris pada suatu file yang mengandung kata yang dicari.
Syntax-nya adalah `grep "[katayangdicari]" [namafile]`
![grep](img/grep.png)

##### 13. zip
Command ini digunakan untuk melakukan compress data menjadi bentuk zip. Syntax-nya adalah ```zip [namafilezip] [file1] [file2]```.
Misalnya kita ingin mengompress file **makanan** dan **cemilan** menjadi  **energi.zip** .
Maka command yang kita jalankan adalah `zip energi makanan cemilan`
![zip](img/zip.png)

##### 14. unzip
Kebalikan dari command zip, unzip digunakan untuk mengekstrak isi dari file .zip
Syntax-nya adalah ```unzip [namafilezip]```.
Jadi untuk mengekstrak file foobar.zip kita perlu menjalankan comman `unzip energi.zip`.
![unzip](img/unzip.png)

##### 15. exit
Digunakan untuk menutup terminal atau mengakhiri suatu script (misalnya saat melakukan ssh ke komputer lain)

##### 16. clear
Digunakan untuk 'membersihkan' isi layar terminal.
Sebelum clear:  
![clear1](img/sebelumclear.png)  
Sesudah clear:  
![clear2](img/sesudahclear.png)

##### 17. tree
Digunakan untuk menampilkan list directory.
Untuk menggunakan command ini, user harus meng-*install*-nya terlebih dahulu dengan command
`sudo apt-get install tree`  
![tree](img/tree.png)

##### 18. mount
Digunakan untuk melakukan mount. Syntax-nya adalah `sudo mount [file/device yang mau di-mount] [directory tempat dia akan di-mount]`
Contoh: ada suatu file _iso_ yang berisi beberapa file. Untuk dapat mengakses file-file di dalamnya melalui terminal, maka kita harus _mount_ file tersebut ke suatu directory.
![mount](img/mount.JPG)  

##### 19. umount
Digunakan untuk melakukan _unmount_. Syntax-nya adalah `umount [directory tempat suatu file/device di-mount]`.
Nama command-nya `umount` yaa bukan _unmount_.
![unmount](img/umount.JPG)  

##### 20. dpkg
Adalah Debian Package Manager. Salah satu kegunaannya adalah untuk meng-install suatu aplikasi yang di-download dari browser.
Syntax-nya adalah `dpkg -i [path ke file installer aplikasi]`
Contohnya adalah saat kalian ingin meng-install _google chrome_ maka kalian dapat menggunakan perintah-perintah di bawah ini:
pertama download dulu installer google chrome yang berekstensi __.deb__
```sh
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```
![wget](img/wget.JPG)  

lalu untuk meng-installnya gunakan command
```sh
$ dpkg -i google-chrome-stable_current_amd64.deb
```
![dpkg](img/dpkg2.jpg)  

### 2. Administrative Command
##### 1. su
Digunakan untuk mengganti user ID atau menjadi superuser.
Syntax-nya adalah `sudo su`

##### 2. sudo
*superuser do*. Digunakan untuk menjalankan command sebagai superuser, superuser biasanya digunakan untuk meng-edit file konfigurasi, mengatur paket, menginstall program.
Syntax-nya adalah `sudo [command]`

###### 3. chown
*change owner*.
+ Digunakan untuk mengubah kepemilikan dari suatu file. Syntax-nya adalah 
```chown [namauser] [namafile]```
![chown](img/chown.png)  
+ Selain user pemilik, command `chown` juga bisa digunakan untuk mengganti *group* pemilik. Syntax-nya adalah
```chown [namauser]:[namagroup] [namafile]```
![chown-group](img/chown2.png)  
**Note:** mohon diingat bahwa nama user dan group yang dipilih harus sudah ada di komputer tersebut.

##### 4. passwd
Digunakan untuk meng-*update* password user.
![passwd](img/passwd.png)  

##### 5. chmod
*change mode*. Digunakan untuk mengubah izin akses dari suatu dokumen.
Contoh syntax `chmod 777 [namafile]`
*777* adalah representasi dari permission yang diberikan. Angka pertama melambangkan permission untuk user, angka kedua untuk group, dan angka ke tiga untuk *Others*
![chmod](img/chmod.png)  

Permission Table

|#|Permission|rwx|Binary|
|---|---|---|---|
|7|read, write and execute|rwx|111|
|6|read and write|rw-|110|
|5|read and execute|r-x|101|
|4|read only|r--|100|
|3|write and execute|-wx|011|
|2|write only|-w-|-1-|
|1|execute only|--x|001|
|0|none|---|000|

### 3. File Editing
##### 1. vim
vim merupakan singkatan dari "Vi IMprovised" dan merupakan salah satu teks editor pada OS Linux yang dapat digunakan untuk mengedit jenis teks apapun, termasuk suatu program komputer. Vim diupgrade dari teks editor vi, yang memiliki beberapa peningkatan dari vi, beberapa diantaranya adalah syntax highlighting, on-line help, multi-windows dan buffers, dll.
Untuk lebih jelas perbedaan antara vim dan vi : https://github.com/vim/vim/blob/master/runtime/doc/vi_diff.txt
##### Install vim teks editor
```sh
$ sudo apt-get update
```
```sh
$ sudo apt-get install -y vim
```
##### Membuat dan meng-insert teks 
Syntax yang biasa digunakan adalah `vim [nama-file]`. Setelah command tersebut dijalankan akan terlihat lambang `~` pada tiap baris yang kosong. 
```sh
$ vim nyoba.txt
```
![vim3](img/vim3.png)

Vim sekarang dalam *mode normal*. Untuk menginsertkan teks, maka ketik `i` untuk masuk ke *mode insert* dan diikuti dengan mengetikkan teks yang diinginkan.
Ketika kita menekan `i` untuk menginsertkan teks, karakter yang kita inputkan akan terketik sesuai dengan posisi kursor saat itu. Agar karakter yang kita inputkan terketik pada sebelah kanan posisi kursor, maka kembalikan vim pada mode normal, dan tekan `a`. Maka karakter yang kita inputkan akan terketik pada sebelah kanan posisi kursor saat itu.

Jika sudah selesai menginputkan teks, tekan `esc` dan vim akan kembali ke mode normal. Dalam mode normal, tekan `h` untuk bergerak ke kiri, `l` untuk ke kanan, `j` untuk bergerak ke atas dan `k` untuk ke bawah.
![vim4](img/vim4.png)

##### Menghapus karakter
Untuk menghapus sebuah karakter, selain bisa dilakukan pada mode insert dapat pula dilakukan ketika vim dalam *mode normal*. Yaitu dengan mengarahkan tanda kursor pada karakter yang ingin dihapus, dan menekan `x`.
Contohnya misal ketika kursor diletakkan pada huruf pertama yaitu huruf *i* pada kalimat *ini baris 3 ya* dan `x` ditekan sebanyak 4 kali, maka kalimat pada baris tersebut yang tersisa adalah *baris 3 ya*.
![vim5](img/vim5.png)

##### Menghapus baris
Jika yang ingin dihapus adalah satu baris penuh, maka yang perlu dilakukan pada *mode normal* yaitu memposisikan kursor pada baris yang ingin dihapus, dan ketikkan `dd`. Misalnya kita ingin menghapus baris pertama dimana terdapat kalimat *hehe :)* maka setelah memposisikan kursor pada baris tersebut, ketika kita mengetikkan `dd` maka baris yang tersisa adalah *nyoba nulis* sebagai baris pertama dan *baris 3 ya* sebagai baris ke-2.
![vim6](img/vim6.png)

##### Menggabungkan dua baris
Untuk menggabungkan dua baris menjadi satu baris atau dengan kata lain menghilangkan spasi diantara 2 baris, maka pada *mode normal* cukup dengan memposisikan kursor pada kalimat di baris pertama dan tekan `J`. Maka kalimat pada baris kedua akan menjadi satu baris dengan kalimat pertama.
![vim7](img/vim7.png)

##### Undo dan Redo
Pada teks editor vim, untuk meng-undo perubahan yang baru saja kita lakukan dilakukan dengan mengetik `u`. Maka pengerjaan yang baru saja kita lakukan akan ter-undo.
Sedangkan untuk me-redo atau kebalikan dari undo yang baru saja kita lakukan yaitu dengan menekan `Ctrl+R`.

##### Menulis pada line baru
Pertama posisikan kursor pada sebuah baris. Untuk membuat line baru dibawah baris tersebut, tekan `o` dan otomatis sebuah baris baru akan terbentuk di bawah kalimat tersebut dengan vim sudah berada pada mode insert. Jika baris yang ingin ditambahkan berada diatas baris tempat kursor berada saat ini, maka dilakukan dengan menekan `O`. 

##### Keluar dari teks editor vim
1. Keluar ketika dalam mode insert tanpa menyimpan perubahan apa-apa dengan mengetikkan `:q!`
2. Keluar ketika dalam mode insert dengan menyimpan perubahan yang dilakukan `:wq`
3. Keluar dan menyimpan perubahan dilakukan pada mode normal dengan mengetikkan `ZZ`

Untuk mengeksplorasi lebih lanjut mengenai teks editor vim, terdapat tutorial vim yang bisa diakses melalui terminal
```sh
$ vimtutor
```

##### 2. gedit
Gedit atau *Gnome-Text-Editor* adalah teks editor untuk GNOME desktop dan dapat digunakan untuk mengedit teks jenis apapun.
Syntax yang biasa digunakan untuk menjalankan teks editor ini adalah 
```sh
$ gedit [nama-file]
```

Misal kita akan membuat file txt dengan nama *cobagedit* maka ketikkan pada terminal
```sh
$ gedit cobagedit.txt
```
Halaman gedit pun akan muncul dan kita bisa menginputkan teks yang kita inginkan.
![gedit1](img/gdit1.png)

File gedit memungkinkan kita untuk mengedit banyak file sekaligus. Syntax yang digunakan 
```sh
$ gedit [file1 file2 ...]
```
misalnya mengedit 2 file yaitu *cobagedit.txt* dan *nyobajuga.txt*
```sh
$ gedit cobagedit.txt nyobajuga.txt
```
![gedit2](img/gdit2.png)

##### 3. nano
Nano atau *Nano's ANOther editor* merupakan teks editor yang dikembangkan mirip dengan teks editor *Pico* yang menjadi editor default dari Pine. Nano termasuk teks editor yang *user-friendly* karena adanya *shortcut* pada bagian bawah editor sehingga memudahkan pengguna dalam menggunakan teks editor ini.
Syntax yang biasa digunakan 
```sh
$ nano [nama-file]
```
![nano1](img/nanoo.png)

Command tersebut akan memunculkan default nano-screen

![nano2](img/nano2.png)

Untuk melihat list dari shortcut-shortcut yang ada tekan `Ctrl+G`

![nano3](img/nano3.png)

Ketika `Ctrl+X` ditekan untuk keluar dari editor, pada bagian bawah di baris ketiga dari bawah akan muncul pertanyaan *Save modified buffer?* Tekan `Y` untuk menyimpan perubahan dari file, dan `N` untuk keluar dari teks editor nano tanpa menyimpan perubahan. 

Selain itu sebelum benar-benar keluar dari teks editor nano, kita juga dapat merubah nama file yang baru saja kita buat tadi. Cukup dengan mengganti nama file sebelumnya yang tertera pada bagian bawah teks editor dimana terdapat tulisan *File name to write: ...* lalu tekan Enter.
![nano4](img/nano4.png)

##### 4. touch
Digunakan untuk membuat sebuah file. Syntax yang digunakan 
```sh
$ touch [nama-file]
```
![touch1](img/touch1.png)

### 4. Export Variable
Command *export* adalah salah satu command yang merupakan bagian dari shell (BuiltIn bash shell). Command ini cukup mudah digunakan karena syntax nya 'langsung' dan hanya memiliki 3 opsi perintah:

- -p : Daftar semua nama yang diekspor dalam shell saat ini
- -n : Hapus nama dari daftar ekspor
- -f : Nama diekspor sebagai fungsi

Secara umum, perintah ekspor menandai *environment variabel* untuk diekspor sehingga proses *child* yang baru bercabang dapat mewarisi semua variabel yang ditandai.

Contoh penggunaan export:

##### Meng-export Proxy
Untuk melakukan export proxy, misalnya menggunakan proxy ITS, maka syntax pada terminal
```sh
$ export http_proxy="http://username%40mhs.if.its.ac.id:password@proxy.its.ac.id:8080"
```
##### Men-set vim sebagai text editor
pada terminal ketikkan command
```sh
$ export EDITOR=/usr/bin/vim
```
Untuk cek hasil export variabel dapat melalui 
```sh
$ export -p
```
atau
```sh
$ export | grep EDITOR
```
![export1](img/export1.png)

##### Me-remove variable dari export list
Digunakan option `-n`
```sh
$ export -n EDITOR
```
### 5. Cek IP dan Koneksi

##### 1. ifconfig
Untuk mengkonfigurasi network interface.
![ifconfig1](img/ifconfig1.png)

##### 2. ping
Merupakan sebuah utility program/alat untuk menguji apakah host tertentu dapat dijangkau.
Syntax yang biasa digunakan
```sh
$ ping [host tujuan]
```
![ping1](img/ping1.png)

##### 3. ssh
ssh adalah suatu network protokol untuk berkomunikasi secara aman antar komputer. ssh menghubungkan dan masuk(log) ke host yang ditentukan. Command ini dapat meremote server SSH komputer lain untuk menjalankan perintah-perintah dari jarak jauh.

ssh akan menyediakan koneksi terenkripsi yang aman antara dua host melalui jaringan yang tidak aman. Sambungan ini juga dapat digunakan untuk akses terminal, transfer file, dan untuk tunneling aplikasi lain.

Syntax yang biasa digunakan
```sh
$ ssh [hostname]
```

### 6. Menginstall Software

##### 1. apt-get update
```sh
$ sudo apt-get update
```
command **apt-get** dengan opsi **_update_** akan menyinkronisasi ulang file indeks paket dari sumber mereka. indeks-indeks dari paket yang tersedia akan diambil dari lokasi-lokasi yang telah ditentukan di _etc/apt/sources.list_.
##### 2. apt-get install pkg
```sh
$ sudo apt-get install <packages>
```
Opsi **install** ini diikuti oleh beberapa nama paket yang akan diinstall. 
Semua paket yang dibuthkan oleh paket yang akan diinstall juga akan terunduh dan terinstall. Berkas /etc/apt/sources.list digunakan untuk menentukan lokasi repositori dari paket yang dimaksud.

##### Referensi
+ https://searchdatacenter.techtarget.com/tutorial/77-Linux-commands-and-utilities-youll-actually-use
+ https://linux.die.net/man/8/apt-get
+ https://www.tutorialspoint.com/unix_commands/export.htm
+ https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/
+ https://linux.die.net/man/1/gedit
+ https://www.computerhope.com/unix/vim.htm
+ https://www.simplified.guide/ubuntu/install-vim
+ https://www.ssh.com/ssh/command/
+ https://linux.die.net/man/8/ifconfig
+ https://en.wikipedia.org/wiki/Chmod
+ https://www.tecmint.com/dpkg-command-examples/
+ https://linuxconfig.org/how-to-install-google-chrome-browser-on-ubuntu-16-04-xenial-xerus-linux
+ https://askubuntu.com/questions/219545/dpkg-error-dpkg-status-database-is-locked-by-another-process
