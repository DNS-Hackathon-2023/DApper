# Use cases

These are the use cases you'll be looking for... eventually.


## Common

Any app that would like to query DNS records (of any type) may require the use of multiple libraries, depending on the programming language and availability, to obtain "all" the results intended.

## Use case 1

An app developer can easily query A records (let's assume also AAAA records). But if they want to query a TXT record (or something else), most basic implementations will not support it.

## Use case 2

Most clould providers (Cloudflare, Azure, AWS, etc.) have very low TTL. If an intensive connecting app (or crawler, etc.) required access for N hours to an address, it would be useful to get the TTL "easily" (i.e. that most DNS libraries would support providing TTL). 

## Use case 3

When some websites are blocked and/or redirected (e.g. for legal reasons), the Extended DNS Errors would be relevant to determine if you are in a legitimate site or a redirected/spoofed one.

## Use case 4



