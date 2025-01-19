# Commitment Issues picoCTF Write-Up

### 1. Unduh File
File yang diperlukan untuk tantangan ini dapat diunduh dengan perintah berikut:
```bash
wget https://artifacts.picoctf.net/c_titan/4/unknown.zip
```

### 2. Ekstrak File ZIP
Setelah diunduh, ekstrak isi file ZIP menggunakan:
```bash
unzip unknown.zip
```

### 3. Gunakan ExifTool untuk Membaca Metadata
Di dalam file yang diekstrak, gunakan **ExifTool** untuk memeriksa metadata dari gambar yang diberikan:
```bash
exiftool ukn_reality.jpg
```

### 4. Identifikasi String Tersembunyi
Saat memeriksa metadata, ditemukan sebuah string pada bidang `Attribution URL`:
```
attribution URL: cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==
```

### 5. Decode String Base64
Decode string tersebut menggunakan perintah berikut:
```bash
echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==" | base64 --decode
```

## Flag
```
picoCTF{ME74D47A_HIDD3N_deca06fb}
```
