```
$ touch index.html .gitattributes README.md
$ echo "secretfile filter=git-crypt diff=git-crypt\ntreasure.key filter=git-crypt diff=git-crypt" >> .gitattributes
$ git add --all
$ git commit -m "init"
$ git-crypt init
$ cat secretfile treasure.key
$ echo "The treasure is burried under the seventh tomb." >> secretfile
$ echo "12 42 99 7 24 7" >> treasure.key
$ git-crypt add-gpg-user "Marc Lundgren <marclundgren2.0@gmail.com>"
$ git push
```

```
$ git-crypt status
not encrypted: README.md
not encrypted: .git-crypt/.gitattributes
not encrypted: .git-crypt/keys/default/0/A85B3DC8A88346E45766198F95BB5D6C1FD87EC3.gpg
not encrypted: .gitattributes
not encrypted: index.html
    encrypted: secretfile
    encrypted: treasure.key
```