# Big Zip picoCTF Write-Up

## Challenge Description
This challenge involves finding a flag within a large collection of files. To solve the challenge, we will use command-line tools such as `wget`, `unzip`, and `grep` to locate the hidden flag.
   
## Solution Steps

1. **Download the ZIP File**  
   Download the ZIP archive containing the files using the following command:
   ```bash
   wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
   ```

2. **Extract the ZIP File**  
   Extract the downloaded ZIP file using the command:
   ```bash
   unzip big-zip-files.zip
   ```

3. **Search for the Flag Using Grep**  
   Use the `grep` command to search for the pattern containing "pico" within the extracted files:
   ```bash
   grep -r pico big-zip-files/
   ```
   The output of this command is as follows:
   ```
   big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
   ```

## Flag
```
picoCTF{gr3p_15_m4g1c_ef8790dc}
```