# Survey of Libraries for DNS querying



# Very very unorganised list:

* Linux
  - getaddrinfo(), etc. (from netdb.h, etc.)
    * https://man7.org/linux/man-pages/man3/getaddrinfo.3.html


* Windows
  - Win32: https://learn.microsoft.com/en-us/windows/win32/dns/dns-functions
  - Win32 POSIX compliance: https://learn.microsoft.com/en-us/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo
    * gettaddrinfo(), getnameinfo(), etc.?

* iOS and related (etc.)
  - ?

* Android
  - ?

* Specifics for BSD, System V, etc.
  - ?

* Specifics for IoT, embedded systems, etc.
  - ?

# High level libraries (very very unorganised) list:
  - libresolv: libresolv is a C library that is commonly used on Unix-like systems for DNS resolution. It provides functions like getaddrinfo() and gethostbyname() for resolving hostnames.
  - java.net.InetAddress: This is a Java library that provides basic DNS resolution capabilities. It allows you to resolve hostnames to IP addresses and vice versa.
  - dnsjava: dnsjava is a DNS implementation library written in Java. It offers a full DNS resolver, DNS server, and client APIs for building DNS-related applications.
  - System.Net.Dns (C#): This is a .NET framework library for DNS resolution in C#. It provides methods to resolve hostnames to IP addresses and perform reverse DNS lookups.
  - [dnspython](https://github.com/rthalley/dnspython): dnspython is a popular DNS toolkit for Python, providing a comprehensive set of DNS functionality. It allows you to perform DNS queries, zone transfers, dynamic updates, and more.
  - [GNU adns](https://www.chiark.greenend.org.uk/ucgi/~ianmdlvl/git/adns.git/): adns is an asynchronous DNS resolver library written in C. It is designed to handle high loads and is commonly used in network applications that require efficient DNS resolution.
  - [C-ares](https://c-ares.org/): C-ares is a C library for asynchronous DNS requests. It offers a non-blocking API for performing DNS queries, making it suitable for high-performance networking applications. (1.6k stars)
  - [node-dns](https://nodejs.org/api/dns.html): node-dns is a DNS library for Node.js. It provides DNS lookup and reverse lookup capabilities and supports features like querying DNS records, resolving hostnames, and handling DNS responses.
  - [Go DNS](https://github.com/miekg/dns): Go DNS is a DNS library for the Go programming language. It provides functions for DNS resolution and manipulation, supporting features like querying DNS records, performing zone transfers, and dynamic updates.
  - [getdns](https://getdnsapi.net) (and also https://getdnsapi.org/documentation/spec/) (~400 stars)
  - rust-dns: rust-dns is a DNS library for the Rust programming language. It provides DNS resolution and manipulation functionalities, including querying DNS records, performing lookups, and building DNS messages.
  - [ldns](https://www.nlnetlabs.nl/projects/ldns/about/): A C library to simplify DNS programming, supporting DNSSEC. (~230 stars)
  - [libidn](https://www.gnu.org/software/libidn/): A library that provides support for internationalized domain names (IDNs).
  - [libunbound](https://github.com/NLnetLabs/unbound/blob/master/libunbound): A validating, recursive, and caching DNS resolver. (part of unbound)
  - [lwres](https://github.com/pspacek/bind/blob/master/doc/design/lwres): A lightweight resolver library. (part of bind)
  - Net::DNS: A Perl module that provides a DNS resolver and client interface.
