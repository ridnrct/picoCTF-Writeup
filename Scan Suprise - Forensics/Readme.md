# Scan Suprise picoCTF Write-Up

### Deskripsi Tantangan
Tantangan ini meminta untuk memindai QR Code dari sebuah gambar di dalam server yang diakses melalui SSH.

### Langkah Penyelesaian

1. **Akses Server Melalui SSH**
   Gunakan perintah berikut untuk masuk ke server:
   ```bash
   ssh -p 60779 ctf-player@atlas.picoctf.net
   ```
   Masukkan kata sandi yang diberikan:
   ```
   1ad5be0d
   ```

2. **Pindai QR Code**
   Gunakan perintah berikut untuk memindai QR Code pada file `flag.png`:
   ```bash
   zbarimg flag.png
   ```

3. **Hasil Pemindaian**
   Output dari perintah di atas adalah sebagai berikut:
   ```
   Connection Error (Failed to connect to socket /var/run/dbus/system_bus_socket: No such file or directory)
   Connection Null
   QR-Code:picoCTF{p33k_@_b00_b5ce2572}
   scanned 1 barcode symbols from 1 images in 0.01 seconds
   ```

### Flag
```
picoCTF{p33k_@_b00_b5ce2572}
```