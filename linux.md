- list package installed: 
```
dpkg --list
```
- remove package:
```
sudo apt-get remove <packagname>
```
- SSH-key github:
```
ssh-keygen -t rsa -b 4096 -C "tuanabcxyz555@gmail.com"
cat .ssh/id_rsa.pub
```

# chmod ~ Change a file's mode
permission to:  user(u)   group(g)   other(o)     
                /¯¯¯\      /¯¯¯\      /¯¯¯\
octal:            6          6          6
binary:         1 1 0      1 1 0      1 1 0
what to permit: r w x      r w x      r w x
binary         - 1: enabled, 0: disabled

what to permit - r: read, w: write, x: execute

permission to  - user: the owner that create the file/folder
                 group: the users from group that owner is member
                 other: all other users
```
chmod 666 /dev/mydevice
```
