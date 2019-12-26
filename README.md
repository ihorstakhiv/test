# Git Secret usage
### Install git secret
Install git secret using following commands

MAC OS ( Install homebrew if required.)
```
brew install git-secret
```
Ubuntu
```
echo "deb https://dl.bintray.com/sobolevn/deb git-secret main" | sudo tee -a /etc/apt/sources.list  wget -qO - https://api.bintray.com/users/sobolevn/keys/gpg/public.key | sudo apt-key add - sudo apt-get update && sudo apt-get install git-secret
```
### Generate GPG key
WARNING: Check your gpg version using command gpg --version. Update gpg if version lover then 2.2 using command
Generate and save your personal GPG key using command
```
gpg --gen-key
```

To get access to encrypted data already added user should add your public GPG key to secret repo:
Copy public GPG key
```
gpg --armor --output public-key.gpg --export user@example.com
```
Send public-key.gpg to already added user. 
Import user key into your gpg setup by running 
```
gpg --import public-key.gpg. 
```
 ### Working with secrets
 Add files for encryption inside your repo
```
git secret add <filenames...>
``` 
Encrypts all added files
```
git secret hide
``` 
Note that you should commit file with .secret extension.
Decrypts  encrypted files
```
git secret reveal
``` 
You can find more git secret commands on https://git-secret.io/
