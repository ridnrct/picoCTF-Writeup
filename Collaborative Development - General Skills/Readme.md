# Collaborative Development picoCTF Write-Up

## Description
This challenge requires extracting the flag from a Git repository. A ZIP file is provided that must be extracted and directed to a directory where there is a Python file named `flag.py`. The flag is hidden in several branches in the Git repository.

### 1. Download and Extract the File
First, download the challenge file using `wget` and extract its contents:
```bash
wget https://artifacts.picoctf.net/c_titan/178/challenge.zip
unzip challenge.zip
```

### 2. Access the "drop-in" Directory
Navigate to the `drop-in` directory that contains the `flag.py` file:
```bash
cd drop-in/
ls
```
The output of the `ls` command shows that there is a `flag.py` file in the directory.

### 3. Inspect the Git Repository
This repository uses Git for version control. Check the list of branches using the following command:
```bash
git branch -a
```
The available branches are:
- `feature/part-1`
- `feature/part-2`
- `feature/part-3`

### 4. Inspect the Contents of Each Branch
Switch to each branch and view the contents of the `flag.py` file to get parts of the flag.

#### a. Branch `feature/part-1`
```bash
git checkout feature/part-1
cat flag.py
```
Output:
```python
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
```
First part of the flag: `picoCTF{t3@mw0rk_`

#### b. Branch `feature/part-2`
```bash
git checkout feature/part-2
cat flag.py
```
Output:
```python
print("Printing the flag...")
print("m@k3s_th3_dr3@m_", end='')
```
Second part of the flag: `m@k3s_th3_dr3@m_`

#### c. Branch `feature/part-3`
```bash
git checkout feature/part-3
cat flag.py
```
Output:
```python
print("Printing the flag...")
print("w0rk_6c06cec1}")
```
Third part of the flag: `w0rk_6c06cec1}`

## Flag 
```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}
```