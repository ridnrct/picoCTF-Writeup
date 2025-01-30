# Scan Surprise picoCTF Write-Up

### Challenge Description
This challenge asks to scan a QR Code from an image on a server accessed via SSH.

### Steps to Solve

1. **Access the Server via SSH**
   Use the following command to log into the server:
   ```bash
   ssh -p 60779 ctf-player@atlas.picoctf.net
   ```
   Enter the provided password:
   ```
   1ad5be0d
   ```

2. **Scan the QR Code**
   Use the following command to scan the QR Code on the `flag.png` file:
   ```bash
   zbarimg flag.png
   ```

3. **Scan Results**
   The output of the above command is as follows:
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