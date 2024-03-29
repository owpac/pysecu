# Pysecu
Small Python script for cryptography (like OpenSSL) based on [Pycryptodome](https://github.com/Legrandin/pycryptodome).

# Installation

### 1. Clone the repo

```
$ git clone https://github.com/Owpac/pysecu
```

### 2. Create venv and install requirements

```
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install -r requirements.txt
```

### 3. Use it !

# How it work

To see help and examples:
```
$ python3 pysecu.py -h
```

1- Hash a file and print the result:
```
$ python3 pysecu.py -i [/path/to/the/file.txt]
```
    
2- Hash a file and save the result in a file:
```
$ python3 pysecu.py -i [/path/to/the/file.txt] -o [/path/to/the/output.txt]
```

3- Generate private and public RSA keys:
```
$ python3 pysecu.py -rsa -o [/path/to/the/key]
```

This command will generate key.pub and key.priv
```
$ python3 pysecu.py -rsa -s {1024 | 2048 | 4096} -p [passphrase] -o [/path/to/the/key]
```

You can change the number of bits with -b option and add a passphrase with -p option.

4- Encrypt a file using public key:
```
$ python3 pysecu.py -i [/path/to/the/file.txt] -pkey [/path/to/the/key.pub] -p [passphrase] -o [/path/to/the/file.bin]
```

5- Decrypt a file using private key:
```
$ python3 pysecu.py -i [/path/to/the/file.bin] -pkey [/path/to/the/key.priv] -p [passphrase] -o [/path/to/the/file.txt]
```

6- Sign a file and verify its signature:
```
$ python3 pysecu.py -i [/path/to/the/file.txt] -s [/path/to/the/mykey.priv] -v [/path/to/the/mykey.pub]
```

If your keys had a passphrase, don't forget to add -p option :
```
$ python3 pysecu.py -i [/path/to/the/file.txt] -s [/path/to/the/mykey.priv] -v [/path/to/the/mykey.pub] -p [passphrase]
```