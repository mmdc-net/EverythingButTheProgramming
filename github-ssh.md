# Creating and Uploading your SSH Key to Github
Type the following commands to create a new key for GitHub:
```bash
$ mkdir -p .ssh             # Make the .ssh directory, if it doesn't exist
$ cd ~/.ssh/                # Change Directory to the .ssh directory
$ ssh-keygen -b 4096        # Create a new key
```
When prompted, name the key "github":
```text
Generating public/private rsa key pair.
Enter file in which to save the key (/home/sk8rboi1996/.ssh/id_rsa): github
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in github.
Your public key has been saved in github.pub.
The key fingerprint is:
SHA256:Eq8t+/G4BJi6bGiOaO5gxRkM593vo6THVdwivt2/CEk sk8rboi1996@snark
The key's randomart image is:
+---[RSA 4096]----+
| . .             |
|  = . .          |
|   + ...  . .    |
|  . oo o.. + .   |
|   +o o S.oE.    |
|  ..   =.o. .    |
|.o.   +.=ooo.    |
|*+..  o*.=.....  |
|O=o  .oo+..  ..o.|
+----[SHA256]-----+
```
Use `ls` to display the files in your .ssh directory:
`$ ls ~/.ssh`
```text
github  github.pub  id_rsa  id_rsa.pub
```
Use `cat` to display the contents of github.pub:
`$ cat github.pub`

Copy the output of `cat`, to paste it into [New Key on GitHub.](https://github.com/settings/ssh/new)
```text
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCziSAt98OJ/JnHjGE9QnviatV2mUnM6W/CFM58uUBobi5saGhBBCZlyBbk7cREFax8nIg1AXFzbHiTZpBhhy0Dmzuq1STIJJE+WA3srBHF41DM7lFZuhjFC9xH9i5l11VWveXssqOWRREmNgs3dwH5X00leHpnmQWc3nUNmJG+qROaMMH4MqbB907cpsWJSMMJ4Rek4nglc3q+XCv8ehE2hag/S98sgjEYtQPaMLcqZGhDoP6gJsxhXRvxksxwhjzmaIsY+4GwczZ2ig8NJ3mAXEs0xxS7lkfFlFywZ1nkQ2RWo8C6hkh2Xm75iW1AxlltexjoPsszuPjJYiy+iPq9laamFOVJN2h1QM9gjHbWCLkMGuWm71A4aZnNn2/qQFn9sVHMFlczH1ZQTYoTr85YH9Nvc0mLR3DqewSXTZ+H+3+yHfzkY6SLXIMOeKn4Ny+MCkWC72pS3Yf/vfIWs1D4bGbDyRFzhLQIKwIg1pdUyduniTkaWbify9QpMDcGQh8SpML6HWG2fwkKORcb1/ILHAgRfQXjedGhZ58Kc6Q9DtIem3B7GBrUdJTLbto7MyGMs7LzOP6VwLBGhHypbFiCy75Ex12VUERaM6s+HktmcqPj7wqH0T6u2m1JpCfe5wDh5v4rWnQSDoFkQzHPO/Bj07TH50Ser20GlLa7Cp3rnw== user@localhost
```
