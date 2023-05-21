# Use cases

These are the use cases you'll be looking for... eventually.


## Common

Any app that would like to query DNS records (of any type) may require the use of multiple libraries, depending on the programming language and availability, to obtain "all" the results intended.

## Use case 1

An app developer can easily query A records (let's assume also AAAA records). But if they want to query a TXT record (or something else), many basic library implementations will not support it (libc, .Net System.Net.DNS, JDK java.net, etc.)

## Use case 2

Most clould providers (Cloudflare, Azure, AWS, etc.) have very low TTL (some zero - this can be considered "evil", see [APNIC - Stop using ridiculously low DNS TTLs](https://blog.apnic.net/2019/11/12/stop-using-ridiculously-low-dns-ttls/) ). If an intensive connecting app (or crawler, etc.) required access for N hours to a specific address, it would be useful to get the TTL "easily" (i.e. that most DNS libraries would support providing TTL), so that the app would optimise the querying strategy.

## Use case 3

When some websites are blocked and/or redirected (e.g. for legal reasons), the Extended DNS Errors would be relevant to determine if you are in a legitimate site or a redirected/spoofed one.

## Use case 4

When an app receives the result of a DNS lookup, there's no detailed information about the validation/security strategy (DNSSEC, DANE, DOH) used, nor the libraries (most? all?) have the possibility of choosing which strategy to use (one is typically hardcoded). It would be useful that libraries (resolvers, etc.) have a priority list to decide which strategies to use and in which order. It would also be useful that the app would receive detailed information about the method used.

## Use case 5
An app uses a DNS library that resolves an address (or DNS record in general). The DNS library generates a high level class object (e.g. System.Net.IPAddress in .Net, java.net.InetAddress in JDK, etc.). The DNS library would take the TTL and using a callback would automatically lookup when the TTL expired (or other strategy), and if the address (or DNS record changed) it would update the class object accordingly. In that case, it could trigger an object event (such as an AddressOnChange event). If the lookup returned the same address, nothing needed to happen and the app would continue to work uninterrupted.

## Use case 6

In an IoT and/or embedded device, knowing why DNS resolution fails is very important. The device programming is usually very resilient to cover all scenarios, so there should be handling of most Extended DNS Errors.

## Use case 7

In an IoT and/or embedded device, validating requests using DNSSEC (etc.) may not always be possible, but the device must be resilient to continue to work regardless. This is very typical in devices implemented in the field where human intervention must be minimal and connectivity needs to prevail.

## Use case 8
In a highly secure environment, connectivity needs to be guaranteed with the proper (and full) validation/security. Anything less than that should be reported to the application, so that the user would know of such issues, and depending on the exact error/warning, the application should handle (or at least report to the use) with different context and possibly different solutions.





