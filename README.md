# Encrypt-Decrypt-data

* ##### To Generate gpg keypair, run : `gpg --generate-key` and follow the instructions

* ##### To list all public keys, run : `gpg -k`

* ##### To list all private keys, run : `gpg -K`


* ##### Example : 
![](https://raw.githubusercontent.com/varunelavia/Encrypt-Decrypt-data/main/Key-List-v2.png)

* ##### In above image, the key id is `2EAF3A12C4F47AFFDA376C08004E197503198231`

* ##### To export public key to a file, run : `gpg --output public.pem --export --armor --Key-ID--`

* ##### To export private key to a file, run : `gpg --output private.pem --export-secret-key --armor --Key-ID--` this is not recommended and should be done at own risk. Do keep private key at a safe place.

* ##### To encrypt a text, run : `echo "<Secret Message>" | gpg --encrypt --armor --output <filename>.txt -r <recipient email address>`
* ##### Example : `echo "This is my Secret, username:hello, password:world" | gpg --encrypt --armor --output my_encrypted_secret.txt -r varunelavia@gmail.com`

* ##### To encrypt a file (it could be anything, txt, png, mp3, mp4, pdf, doc, xls etc), run : `gpg --encrypt --armor --output <filename>.txt -r varunelavia@gmail.com <File to encrypt>`
* ##### Example : `gpg --encrypt --armor --output my-important-image.txt -r varunelavia@gmail.com My-Important-Image.png`

* ##### To decrypt a file, run : `gpg --decrypt --output <output filename> <encrypted filename>.txt`

* ##### Example : `gpg --decrypt --output My-Secret-Image.png my-important-image.txt`

* ##### To delete public key, run : `gpg --delete-keys <key id>`
* ##### To delete private key, run : `gpg --delete-secret-keys <key id>`
* ###### Note : if you attempt to delete public key first and if associated private key is on your machine then deletion will fail. You need to delete private key first and then the public key.

* ##### To import public or private key, run : `gpg --import <filename>`
* ##### Example : `gpg --import public.pem`, `gpg --import private.pem`
