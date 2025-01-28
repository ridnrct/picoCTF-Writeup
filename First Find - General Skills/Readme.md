# First Find picoCTF Write-Up

## Deskripsi Tantangan
Tantangan ini melibatkan pencarian sebuah file tersembunyi bernama `uber-secret.txt` yang berada dalam struktur direktori yang dalam. File ini mengandung flag yang diperlukan untuk menyelesaikan tantangan.

## Langkah Penyelesaian

1. **Ekstraksi File**
   Proses ekstraksi file menghasilkan daftar file dan direktori seperti berikut:
   ```
   inflating: files/satisfactory_books/23765.txt.utf-8  
   inflating: files/satisfactory_books/16021.txt.utf-8  
   inflating: files/13771.txt.utf-8   
    extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
   inflating: files/adequate_books/more_books/1023.txt.utf-8  
   inflating: files/adequate_books/46804-0.txt  
   inflating: files/adequate_books/44578.txt.utf-8  
   inflating: files/acceptable_books/more_books/40723.txt.utf-8  
   inflating: files/acceptable_books/17880.txt.utf-8  
   inflating: files/acceptable_books/17879.txt.utf-8  
   inflating: files/14789.txt.utf-8
   ```
   File `uber-secret.txt` ditemukan pada jalur:
   ```
   files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
   ```

2. **Baca File yang Relevan**
   Gunakan perintah `cat` untuk membaca file dan mendapatkan flag:
   ```
   cat files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
   ```

3. **Flag Ditemukan**
   Output dari perintah di atas adalah:
   ```
   picoCTF{f1nd_15_f457_ab443fd1}
   ```

## Flag
```
picoCTF{f1nd_15_f457_ab443fd1}
```
