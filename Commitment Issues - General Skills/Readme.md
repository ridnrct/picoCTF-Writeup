# Commitment Issues picoCTF Write-Up

### 1. **HEAD: Pointer Git yang Menunjuk ke Commit Terakhir**

Dalam Git, **HEAD** merupakan pointer yang menunjuk ke commit terakhir yang sedang aktif pada cabang (branch) yang sedang digunakan. 

### 2. **HEAD Mengarah pada `refs/heads/master` yang Berisi Hash `42942c9c605b30100f5d859ef6e172027447c0db`**

Pada repositori ini, **HEAD** menunjuk pada cabang `master`, yang berarti cabang utama yang aktif dalam repositori. Hal ini terlihat pada file `.git/HEAD`, yang menunjuk ke `refs/heads/master`. Commit terbaru di cabang ini memiliki hash `42942c9c605b30100f5d859ef6e172027447c0db`.

### 3. **Perintah `git show` Melihat Informasi Detail tentang Commit**

Perintah `git show` adalah alat yang sangat berguna untuk memeriksa detail dari sebuah commit tertentu. Dengan menggunakan `git show`, mendapatkan informasi lebih lanjut mengenai commit, termasuk:
- **Perubahan File**: Menunjukkan file yang diubah dalam commit tersebut.
- **Author**: Siapa yang melakukan perubahan.
- **Tanggal Commit**: Kapan commit tersebut dilakukan.
- **Pesan Commit**: Deskripsi dari commit yang menjelaskan perubahan yang dilakukan.

Perintah ini membantu untuk memverifikasi perubahan yang diterapkan pada repositori dengan lebih mendalam.

### 4. **Contoh Penggunaan `git show`**

Untuk melihat detail dari commit dengan hash `42942c9c605b30100f5d859ef6e172027447c0db`, dapat menjalankan perintah berikut:
```bash
git show 42942c9c605b30100f5d859ef6e172027447c0db
```

## Flag
Hasil program mencetak flag berikut:
```
picoCTF{s@n1t1z3_c785c319}
```
