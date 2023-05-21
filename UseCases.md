# Use cases

These are the use cases you'll be looking for... eventually.


## Common

Any app that would like to query DNS records (of any type) may require the use of multiple libraries, depending on the programming language and availability, to obtain "all" the results intended.

## Use case 1

An app developer can easily query A records (let's assume also AAAA records). But if they want to query a TXT record (or something else), most basic library implementations will not support it.

## Use case 2

Most clould providers (Cloudflare, Azure, AWS, etc.) have very low TTL (some zero). If an intensive connecting app (or crawler, etc.) required access for N hours to a specific address, it would be useful to get the TTL "easily" (i.e. that most DNS libraries would support providing TTL), so that the app would optimise the querying strategy.

## Use case 3

When some websites are blocked and/or redirected (e.g. for legal reasons), the Extended DNS Errors would be relevant to determine if you are in a legitimate site or a redirected/spoofed one.

## Use case 4

When an app receives the result of a DNS lookup, there's no detailed information about the validation/security strategy (DNSSEC, DANE, DOH) used, nor the libraries (most? all?) have the possibility of choosing which strategy to use (one is typically hardcoded). It would be useful that libraries (resolvers, etc.) have a priority list to decide which strategies to use and in which order. It would also be useful that the app would receive detailed information about the method used.






