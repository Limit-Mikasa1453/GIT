# :coffee: CARA INSTALLASI GIT DI LINUX
**For Ubuntu, this PPA provides the latest stable upstream Git version**
```ruby
$ apt-get install git
```
**try your cli linux**
* [install git di linux](https://git-scm.com/download/linux)


# :coffee: GIT DASAR
### `git init` membuat repository supaya bisa dimonitoring oleh git (ketik perintah pada folder yang akan dijadikan repository)
```ruby
$ git init
```

### `git add` menambahakan file baru ke staging area 

- menambahkan semua file dengan `titik`
```ruby
$ git add . 
```
- menambahkan semua file dengan `nama_file` lansung (satu persatu)
```ruby
$ git add nama_file.ext
```

### `git commit` menyimpan perubahan pada file
- menyimpan perubahan dengan perintah `-m` (setelah file add ke `staging area`)
```ruby
$ git commit -m "your_comment"
```
- menyimpan perubahan dengan perinta `-am` tanpa setelah file add ke `staging area` (update perubahan file)
```ruby
$ git commit -am "your_comment"
```

### `git status` melihat perubahan yang terjadi pada repository
```ruby
$ git status
``` 

### `git branch` cek branch
- cek nama2 branch dan branch aktif
```ruby
$ git branch
```
- menambahkan branch baru
```ruby
$ git branch <new_branch>
```
- menghapus branch
```ruby
$ git branch -d <nama_branch>
```
- menghapus branch (forced)
```ruby
$ git branch -D <nama_branch>
```
- rename nama branch
```ruby
$ git branch -m <old_branch> <new_branc>
```

### `git merge` mengabungkan data file dari dua branch
 > type2 git marege ada duag : fast-forward Merge & three-way Merge / Merge commit
```ruby
$ git merge
```
   
   
### `git rebase`  digunakan untuk menggabungkan atau menggeser commit base (cabang branch to branch utama)
```ruby
$ git rebase
```

### `git checkout` digunakan untuk berpindah commit atau bisa juga di gunakan untuk sebagai switch branch
- berpindah ke komit yg sebelumnya
```ruby
$ git checkout <7_digit_code_hash> <nama_file.ext>
``` 
- switch to branch
```ruby
$ git checkout [nama_branch] 
```
- switch to branch and add new branch
```ruby
$ git checkout -b [nama_branch] 
```

### `git log` digunakan untuk melihat history perubahan pada repository 
- view all history
```ruby
$ git log 
```
- view 3 history terakhir
```ruby
git log -3
```
- view graphic history
```ruby
$ git log --all --decorate --oneline --graph
```

### fungsi `alias` digunakan untuk menyinkaat script pada linux 
```ruby
$ alias git_graph="git log --all --decorate --oneline --graph"
```

### `git clone` digunakan untuk menduplikat repository dari github ke pc
```ruby
$ git clone <https or ssh or cli>
```
   
### git remote digunakan cek alamat remote pada github
```ruby
$ git remote
$ git remote -v
```

### `git push` sync pc vs github
```ruby
$ git push
```
  
### `git pull` merge remote to pc
```ruby
$ git pull 
$ git pull <nama_origin> <branch_name>
```
  
### `git fetch` cek history commit pada remote github
```ruby
$ git fetch 
```

### list configurasi git
```ruby
$ git config --list
$ git config --<global or local or system> user.name "yourusername"
$ git config --<global or local or system> user.email "youremail@gmail.com"
```


# CREATE REMOTE (on github tidak ada repo tapi kita punya git di local)
- buat repository di github & uncheck readme.md
- jalankan perintah di bawah ini untuk pust git local to github pada local computer
```ruby
$ git remote add <nama_origin> git@github.com:<username_github>/<repo>.git
$ git branch -M <nama_branch>
$ git push -u <nama_origin> <nm_brc>
$ git push -u <nama_origin> HEAD:<nm_brc>

```

# :coffee: CREATE TOKEN HTTPS CLONE GITHUB
> password token exampel : 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

# :coffee: CREATE SSH KEY CLONE GITHUB
```ruby
$ cd ~/.ssh
$ ls 
```
- command to generate a new key pair
```ruby
$ ssh-keygen -o -t rsa -C "your@email.com"
``` 
> Generating public/private rsa key pair.
Enter file in which to save the key (`/Users/username/.ssh/id_rsa`): pilih `enter for default`

> Enter passphrase (empty for no passphrase):
  Enter same passphrase again: `enter for no passphrase`
- Add your public key to GitHub
```ruby
$ cat ~/.ssh/id_rsa.pub 
```  
    


# :coffee: .GITIGNORE
- create file <.gitignore> in your repository
- isi file git .ignore example :
```ruby
cofig.txt 
data/ 
*.exe 
```


## :coffee: resources
* [Basic writing and formatting syntax on github](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [create SSH Keys](https://jdblischak.github.io/2014-09-18-chicago/novice/git/05-sshkeys.html#:~:text=Login%20to%20github.com%20and,hit%20Add%20key%20to%20save.)
* [git docs](https://git-scm.com/docs)
* [git .ignore](https://github.com/github/gitignore)
* [git ignore.io](https://gitignore.io)
