Looking at Debian:

* about 30k source packages

* [2273](curl -s https://codesearch.debian.net/results/68491d1a4fe093f0/packages.txt) use gethostbyname
* [1953](https://codesearch.debian.net/results/efdda8e64d80b539/packages.txt) use getaddrinfo
* ~10 use adns
* ~30 use c-ares
* there are no users of libgetdns besides python3-getdns (which has no users)
* ~130 use dnspython
* ~10 use python-dns
* ~5 use python3-aiodns
* ~15 use ldns
