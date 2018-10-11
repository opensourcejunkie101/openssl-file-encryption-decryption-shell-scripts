# OpenSSL file encryption / decryption shell scripts

Cipher: AES-256 in CBC mode

https://en.wikipedia.org/wiki/Advanced_Encryption_Standard

https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Cipher_Block_Chaining_(CBC)

Message digest algorithm: SHA-256

https://en.wikipedia.org/wiki/SHA-2

These scripts have been created for general use under the LICENSE terms.

They are standard POSIX shell scripts, so you most probably can run it in every Linux environment.

https://en.wikipedia.org/wiki/POSIX

https://en.wikipedia.org/wiki/Unix_shell

They should contain every safety measure / error check, that I thought of.

Multiple arguments (files) are currently not supported.


----------------------------------------------------


# Download and Installation


1. Download it from this repository using `git`:
    ```
    git clone https://github.com/burianvlastimil/openssl-file-encryption-decryption-shell-scripts
    ```

2. Go to the downloaded directory:
    ```
    cd openssl-file-encryption-decryption-shell-scripts/
    ```

3. You may either copy it manually, or install it to `/usr/local/bin` using bundled `Makefile`:
    ```
    sudo make install
    ```
   
   You may also **override the default destination location** using `DESTDIR`:
   ```
   sudo DESTDIR=/usr/bin make install
   ```
   
   Note for Cygwin users: You do not need / actually cannot to use `sudo`, just omit it.


----------------------------------------------------


# Uninstallation / Removal

It is as simple as the installation method you chose.
If you have chosen to use the `Makefile` method, it is as simple as:

```
sudo make uninstall
```


----------------------------------------------------


# Usage

1. Encryption

    ```
    encrypt-file-aes256 filename
    ```

    will always produce the `filename` with `.enc` extension, even if you encrypt a file multiple files, for instance the following file:

    ```
    filename.enc.enc.enc
    ```

    has been encrypted 3 times.

2. Decryption

    ```
    decrypt-file-aes256 filename.enc
    ```
    
    will strip the defined `.enc` extension and produce a file named:
    
    ```
    filename
    ```
    
    But it has to be possible to decrypt files without the defined extension.
    In this case we will append `.dec` to the filename and produce for example:
    
    ```
    filename.dec
    ```


----------------------------------------------------


# Exit codes

0 - Successful encryption / decryption.

1 - One argument needs to be given. Both relative, and absolute file paths are supported.

2 - Multiple arguments are not supported.

3 - The given argument is not an existing file.

4 - Input file is not readable by you.

5 - Destination directory is not writable by you.

6 - Destination file exists.

7 - Failed encryption / decryption.


----------------------------------------------------

# Testing

I did the following tests so far:

- every fail exit code has been tested: PASS

- encrypting / decrypting a very small file, 1 KB: PASS

- encrypting / decrypting a medium size file, 15 GB: PASS

- encrypting / decrypting a very large file, 750 GB: PASS

----------------------------------------

# If you like the script, consider donating any amount to my cryptocurrency accounts

**Bitcoin**
```
32fD1Qkx5Kf6GbjewTLhBkjrZGryYjTotS
```

**Bitcoin Cash**
```
qrsh8dwwrpvdxj6le8gvv9uq0u72zzmjzvger0qzd6
```

**Ethereum**
```
0x2537a26e5F8AF085Fce9fBe0e45BDA6dBa0c0349
```

**Ethereum Classic**
```
0x3fbf8Cba84FAB0F3Bd5aaa7a81663e4831fb5eC4
```

**Litecoin**
```
MNg1JdTmC1FmYLiGiB5XzRRXJVg325X84Y
```

Thank you!

----------------------------------------------------


# Reporting bugs and suggestions

Please send an email to me: info@vlastimilburian.cz
