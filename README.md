A toy program that can print its own source code:

```
$ git clone https://github.com/stfnw/git-quine && cd git-quine
$ git checkout tags/git-quine

$ python3 git-quine.py quine > git-quine.py2
$ sha256sum git-quine.py*
7e35130735fb671f8498600e0de7baf87084411c3d8f30ea6d20dfc9fef955ce  git-quine.py
7e35130735fb671f8498600e0de7baf87084411c3d8f30ea6d20dfc9fef955ce  git-quine.py2
```

And can print its own commit hash:

```console
$ git clone https://github.com/stfnw/git-quine && cd git-quine
$ git checkout tags/git-quine

$ python3 git-quine.py
################################################
# Printing some stats about my own source code #
################################################

[+] file length:    21068
[+] file sha512sum: 4661b617d241260e517a4d01f0a52e84321f2293de074364d2a042286ac49c659a72ca576eb592aa06d9e3c5a01b7de69f60911c79efe38b1a4bebdab4ad16e4

[+] git BLOB_HASH:       9ad71ad549bc1c0f5a57b0f17b8eb8dc0029215f

[+] git TREE_HASH:       00bf3d9a7c022ebbb81b67ede88eee96bb87b145
[+] git TREE contents:   b'tree 40\x00100644 git-quine.py\x00\x9a\xd7\x1a\xd5I\xbc\x1c\x0fZW\xb0\xf1{\x8e\xb8\xdc\x00)!_'

[+] git COMMIT_HASH:     e539f2f3841da633c9da81ab7878580daf65ea6c
[+] git COMMIT contents: b'commit 279\x00tree 00bf3d9a7c022ebbb81b67ede88eee96bb87b145\nauthor Stefan Walter <stefan [underscore] walter [at] posteo [dot] de> 1733958000 +0100\ncommitter Stefan Walter <stefan [underscore] walter [at] posteo [dot] de> 1733958000 +0100\n\ngit-quine: a program that prints its own commit hash\n'

$ sha512sum git-quine.py
4661b617d241260e517a4d01f0a52e84321f2293de074364d2a042286ac49c659a72ca576eb592aa06d9e3c5a01b7de69f60911c79efe38b1a4bebdab4ad16e4  git-quine.py

$ git log
commit e539f2f3841da633c9da81ab7878580daf65ea6c (HEAD, tag: git-quine, main)
Author: Stefan Walter <stefan [underscore] walter [at] posteo [dot] de>
Date:   Thu Dec 12 00:00:00 2024 +0100

    git-quine: a program that prints its own commit hash

```
