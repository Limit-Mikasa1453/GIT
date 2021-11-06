# GIT CLONE ON LINUX
pada hari ini 6 nov 2021 saya ingin `clone repo` dari github menggunakan `ssh` dengan perintah
```ruby
$ git clone git@github.com:user_github/repo.git
```
pada saat proses bukannya berhasil tapi malah muncul pesan error:
`git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.`. 
padahal sebelumnya saya sudah mencobanya dan berhasil. saya coba search di google ketemu [blog punya github](https://docs.github.com/en/authentication/troubleshooting-ssh/error-permission-denied-publickey) lansung yang mempunyai pesan error yang sama yaitu `Error: Permission denied (publickey)` saya ikutinlah cara2nya tapi tetep ga bisa. so jadi saya hapus [ssh lama](https://github.com/settings/keys) dan bikin [ssh baru](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh). setelah saya bikin ssh baru lansung tuh saya cobain dan berhasil... wet..wet tapi ternyata saya salah memposisikan directory pada saat clone, directory masih di `/home/mikasa/.ssh/` terus saya hapus repo git cloningnya saya pindah repo htdoct di linux `/opt/lampp/htdocs` ketika saya coba teryata masih muncul keterangan error yang sama meskipun sudah menggunakan `sudo` super user. hmmm.. apa lgi ya... karena keterangan errornya adalah permitions saya coba cek permitions folder/direcory htdoct ternyata permitionsnya adalah drwx-wx-wx. saya coba rubah permitionnya jadi 777 supaya full akses dari user lain dengan preintah `sudo chmod -R 777 htdocs`. dan saya coba jalankan lgi clone menggunakan ssh nya dan berhasil.

## kesimpulan
- jalan clone dengan super user
 ```ruby
$ sudo git clone git@github.com:user_github/repo.git
```
- pastikan folder htdoct full akses
```ruby
$ ls /opt/lampp/htdocs -la
```
- rubah akses directory htdocs besarta isinya
```ruby
$ sudo chmod -R /opt/lampp/htdocs
```
- atau rubah akses directory nya saja
```ruby
$ sudo chmod /opt/lampp/htdocs
``` 


## resources : 
* [git_ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)
