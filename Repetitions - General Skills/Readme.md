# Repetitions picoCTF Write-Up

## Challenge Description
This challenge involves a file named `enc_flag` that contains an encrypted string in Base64 format. The goal of the challenge is to decode the string six times until finally obtaining the flag in the format `picoCTF{}`.

The `enc_flag` file contains the following string:
```
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVhRmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNkMlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVWVkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZsaGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```

## Solution Steps

1. **Read File**
   Copy the contents of the `enc_flag` file which contains the encrypted string. Ensure that the string is in Base64.

2. **Decode Base64**
   Use a tool or script to decode the Base64 string six times. Using Python, command line tools, or online tools (https://www.base64decode.net/). Here are the steps with Python:

   ```python
   import base64

   encoded_flag = "VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVhRmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNkMlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVWVkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZsaGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg=="

   for i in range(6):
       encoded_flag = base64.b64decode(encoded_flag).decode('utf-8')

   print(f"Decoded Flag: {encoded_flag}")
   ```

## Python Code Explanation
- **`base64.b64decode`**: Function to decode a Base64 string.
- **`range(6)`**: Repeats the decode process six times.
- **`decode('utf-8')`**: Converts the decoded result from bytes to string.

3. **Result**
   After running the decode process six times, you will get the flag:
   ```
   picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
   ```

## Flag
```
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
```
