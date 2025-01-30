# First Find picoCTF Write-Up

## Challenge Description
This challenge involves finding a hidden file named `uber-secret.txt` located deep within a directory structure. This file contains the flag needed to complete the challenge.

## Solution Steps

1. **File Extraction**
   The file extraction process yields a list of files and directories as follows:
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
   The file `uber-secret.txt` is found at the path:
   ```
   files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
   ```

2. **Read the Relevant File**
   Use the `cat` command to read the file and obtain the flag:
   ```
   cat files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
   ```

3. **Flag Found**
   The output of the above command is:
   ```
   picoCTF{f1nd_15_f457_ab443fd1}
   ```

## Flag
```
picoCTF{f1nd_15_f457_ab443fd1}
```
