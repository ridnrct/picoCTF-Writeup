# Commitment Issues picoCTF Write-Up

### 1. Download File
The file needed for this challenge can be downloaded with the following command:
```bash
wget https://artifacts.picoctf.net/c_titan/4/unknown.zip
```

### 2. Extract ZIP File
After downloading, extract the contents of the ZIP file using:
```bash
unzip unknown.zip
```

### 3. Use ExifTool to Read Metadata
Inside the extracted file, use **ExifTool** to examine the metadata of the given image:
```bash
exiftool ukn_reality.jpg
```

### 4. Identify Hidden String
While examining the metadata, a string was found in the `Attribution URL` field:
```
attribution URL: cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==
```

### 5. Decode Base64 String
Decode the string using the following command:
```bash
echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==" | base64 --decode
```

## Flag
```
picoCTF{ME74D47A_HIDD3N_deca06fb}
```
