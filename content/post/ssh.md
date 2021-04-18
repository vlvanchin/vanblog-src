+++
title = "SSH"
description = "This page shows some basic commands used in SSH"
tags = [
    "ssh",
]
date = "2021-03-14"
categories = [
    "ssh",
]
menu = "main"
author = "van"
+++

# ssh-keygen

This section shows some of the useful commands for Ssh-keygen.

## how to generate ssh keypair

```
$ ssh-keygen // uses all the default to generate the keypair
```

* to generate with different filename
```
$ ssh-keygen -f <filename>
```

* to generate with different type of coding, RSA, DSA
```
$ ssh-keygen -t <code type>
```

* to generate with number of bits
```
$ ssh-keygen -b 2048
```

* to generate with a comment
```
$ ssh-keygen -C <comment | email>
```

* to generate key pair with new passpharse (empty string)
```
$ ssh-keygen -N "" 
```

* to generate a key pair in PEM format with comments and save it to a different filename
```
$ ssh-keygen -m PEM -C "my special vm" -f my_special_vm.pem
```

## how to add a passphrase to the existing keys

```
$ ssh-keygen -p -f <filename>
```

## to list the associated public key for any private key
```
$ ssh-keygen -y -f <private-key-filename>
```

## how to upload the public key to "my special vm" machine, so that i would not be required to key in my credentials each time
```
$ ssh-keygen -y -f my_special_vm.pem | ssh <username>@<server_domain_name-or-ip_address> 'cat >> ~/.ssh/authorized_keys'

or

$ ssh-copy-id -i linux_academy.pem.pub <username>@<server_domain_name-or-ip_address>
```

## File/folder permission to be set 

* the folder persmission where all the ssh keys are housed should be `0700`.

* the files below should be configured with `0644`
	* authorized_keys
	* known_hosts
	* config
	* all .pub files

* the private key files should be with `0600`

## to display the contents of know_hosts file 

```
$ ssh-keygen -lv -f known_hosts
```

## to hash the keys of the known_hosts

```
$ ssh-keygen -H -f known_hosts
```

