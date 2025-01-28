# Big Zip picoCTF Write-Up

## Deskripsi Tantangan
Tantangan ini melibatkan mencari sebuah flag dalam kumpulan file yang besar. Untuk menyelesaikan tantangan, kita akan menggunakan perintah command-line seperti `wget`, `unzip`, dan `grep` untuk menemukan flag yang tersembunyi.

## Langkah Penyelesaian

1. **Unduh File ZIP**
   Unduh arsip ZIP yang berisi file dengan menggunakan perintah berikut:
   ```bash
   wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
   ```

2. **Ekstrak File ZIP**
   Ekstrak file ZIP yang telah diunduh menggunakan perintah:
   ```bash
   unzip big-zip-files.zip
   ```

3. **Cari Flag dengan Grep**
   Gunakan perintah `grep` untuk mencari pola yang mengandung "pico" di dalam file yang telah diekstrak:
   ```bash
   grep -r pico big-zip-files/
   ```
   Output perintah tersebut adalah sebagai berikut:
   ```
   big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
   ```

## Flag
```
picoCTF{gr3p_15_m4g1c_ef8790dc}
```