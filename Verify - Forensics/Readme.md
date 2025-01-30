# Verify picoCTF Write-Up

### Analyzing the Given File

- **`checksum.txt`** contains the hash:

  ```
  3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4
  ```

- **`decrypt.sh`** is the following shell script:

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

  This script uses OpenSSL to decrypt a file encrypted with the AES-256-CBC algorithm. The password is `picoCTF`.

### Identifying the Correct File

The hash in `checksum.txt` is the SHA-256 of one of the files in the `files/` directory.
To find the matching file, calculate the SHA-256 hash of each file in that directory:

```bash
find files/ -type f -exec sha256sum {} + | grep "3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4"
```

The result shows the matching file:

```
3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4  files/e018b574
```

### Decrypting the File

Decrypt the found file using the provided `decrypt.sh` script:

```bash
./decrypt.sh files/e018b574
```

## Flag

```
picoCTF{trust_but_verify_e018b574}
```
