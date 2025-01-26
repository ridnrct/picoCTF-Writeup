# Repetitions picoCTF Write-Up

## Deskripsi Tantangan
Tantangan ini melibatkan sebuah file bernama `enc_flag` yang berisi string terenkripsi dalam format Base64. Tujuan dari tantangan adalah mendekode string tersebut sebanyak enam kali hingga akhirnya mendapatkan flag dalam format `picoCTF{}`.

File `enc_flag` berisi string berikut:
```
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVhRmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNkMlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVWVkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZsaGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```

## Langkah Penyelesaian

1. **Baca File**
   Salin isi file `enc_flag` yang berisi string terenkripsi. Pastikan bahwa string tersebut adalah Base64.

2. **Dekode Base64**
   Gunakan alat atau skrip untuk mendekode string Base64 sebanyak enam kali. Menggunakan Python, command line tools, atau alat online(https://www.base64decode.net/). Berikut adalah langkah-langkah dengan Python:

   ```python
   import base64

   encoded_flag = "VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVhRmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNkMlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVWVkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZsaGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg=="

   for i in range(6):
       encoded_flag = base64.b64decode(encoded_flag).decode('utf-8')

   print(f"Decoded Flag: {encoded_flag}")
   ```
## Penjelasan Kode Python
- **`base64.b64decode`**: Fungsi untuk mendekode string Base64.
- **`range(6)`**: Mengulangi proses dekode sebanyak enam kali.
- **`decode('utf-8')`**: Mengubah hasil dekode dari byte ke string.

3. **Hasil**
   Setelah menjalankan dekode sebanyak enam kali, akan mendapatkan flag:
   ```
   picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
   ```

## Flag
```
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
```
