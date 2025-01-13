# Verify picoCTF Write-Up

### 1. Menganalisis File yang Diberikan

- **`checksum.txt`** berisi hash:

  ```
  3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4
  ```

- **`decrypt.sh`** adalah skrip shell berikut:

  ```bash
  #!/bin/bash
  if [ $# -eq 0 ]; then
      echo "Expected usage: decrypt.sh <filename>"
      exit 1
  fi

  file_name="$1"
  if [ ! -f "/home/ctf-player/drop-in/$file_name" ]; then
      echo "Error: '$file_name' is not a valid file. Look inside the 'files' folder with 'ls -R'!"
      exit 1
  fi

  if ! openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -salt -in "/home/ctf-player/drop-in/$file_name" -k picoCTF; then
      echo "Error: Failed to decrypt '$file_name'. This flag is fake! Keep looking!"
  fi
  ```

  Skrip ini menggunakan OpenSSL untuk mendekripsi file yang dienkripsi dengan algoritma AES-256-CBC. Kata sandinya adalah `picoCTF`.

### 2. Mengidentifikasi File yang Tepat

Hash yang terdapat dalam `checksum.txt` adalah SHA-256 dari salah satu file dalam direktori `files/`.
Untuk menemukan file yang cocok, menghitung hash SHA-256 dari setiap file di direktori tersebut:

```bash
find files/ -type f -exec sha256sum {} + | grep "3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4"
```

Hasilnya menunjukkan file yang cocok:

```
3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4  files/e018b574
```

### 3. Dekripsi File

Dekripsi file yang ditemukan menggunakan skrip `decrypt.sh` yang sudah diberikan:

```bash
./decrypt.sh files/e018b574
```

Hasilnya adalah:

```
picoCTF{trust_but_verify_e018b574}
```
