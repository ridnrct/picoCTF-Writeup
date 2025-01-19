# Collaborative Development picoCTF Write-Up

## Deskripsi
Tantangan ini mengharuskan untuk mengekstrak flag dari repositori Git. Diberikan file ZIP yang harus diekstrak dan diarahkan ke direktori tempat terdapat file Python bernama `flag.py`. Flag tersembunyi di beberapa cabang (branches) di repositori Git.

### 1. Unduh dan Ekstrak File
Pertama, unduh file tantangan menggunakan `wget` dan ekstrak isinya:
```bash
wget https://artifacts.picoctf.net/c_titan/178/challenge.zip
unzip challenge.zip
```

### 2. Akses Direktori "drop-in"
Pindah ke direktori `drop-in` yang berisi file `flag.py`:
```bash
cd drop-in/
ls
```
Hasil perintah `ls` menunjukkan ada file `flag.py` di direktori tersebut.

### 3. Periksa Repositori Git
Repositori ini menggunakan Git untuk mengelola versi. Periksa daftar cabang menggunakan perintah berikut:
```bash
git branch -a
```
Cabang yang tersedia adalah:
- `feature/part-1`
- `feature/part-2`
- `feature/part-3`

### 4. Periksa Isi Masing-Masing Cabang
Pindah ke setiap cabang dan lihat isi file `flag.py` untuk mendapatkan bagian dari flag.

#### a. Cabang `feature/part-1`
```bash
git checkout feature/part-1
cat flag.py
```
Output:
```python
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
```
Bagian pertama flag: `picoCTF{t3@mw0rk_`

#### b. Cabang `feature/part-2`
```bash
git checkout feature/part-2
cat flag.py
```
Output:
```python
print("Printing the flag...")
print("m@k3s_th3_dr3@m_", end='')
```
Bagian kedua flag: `m@k3s_th3_dr3@m_`

#### c. Cabang `feature/part-3`
```bash
git checkout feature/part-3
cat flag.py
```
Output:
```python
print("Printing the flag...")
print("w0rk_6c06cec1}")
```
Bagian ketiga flag: `w0rk_6c06cec1}`

## Flag 
```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}
```