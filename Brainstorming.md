# Brainstorming

**NB! Work in progress**

## Goals

The primary goals of the DApper project are:

- Develop an EDE (Extended DNS Errors) testbench
- Draft problem statements
- Conduct an application gap analysis


## Target Platforms

During the Hackathon, we considered just three platforms.

- Linux
- BSD
- MS Windows

Future work might consider other platforms, perhaps including

- macOS
- Android
- IOS

## Typical current use the of DNS in applications

For address resolution, the familiar and reliable `getaddrinfo()` is
widely used, and supports both IPv4 and IPv6.  Some applications cache
addresses obtained in this way, in order to avoid the anticipated cost
of repeated calls to `getaddrinfo()`.

For other record types, the developer's (or developer team's)
preferred resolver library is linked with the application, and ad-hoc
code in the application invokes resolver functions to retrieve the
desired records.

## Problem Statement

The `getaddrinfo()` function does not indicate the valid lifetime
(TTL) of the address data it provides to the application. On the other
hand, some hostnames represent a constellation of replicas of the same
content, among which load is balanced using the DNS; in such a case,
the TTL announced in the DNS is typically very short. Any mismatch
between the respective timers used by the applications cache managemnt
strategy and the content providers load-balancing strategy may
frustrate the intent of both parties.





## Elements of the solution



- DNSSEC (Domain Name System Security Extensions)
- Local cache (e.g., Windows DNS Client service)
- Routability
- Reachability
- IPv4/IPv6 dual stack
- Happy Eyeballs algorithm
- Various DNS records, such as A/AAAA, HTTPS/SVCB, TXT, SRV, URL, and TLSA

## Resources

DApper utilizes resources from Windows, BSD, and Linux/GNU libraries.

## Application Expectations & Enhancements

### Expectations

DApper aims to provide:

- A `getaddrinfo` chain or a simple `connect` function
- Overhead amortization, e.g., in-app cache
- Access to auxiliary records using ad hoc code
- Asynchronous operation and thread-safety

### Enhancements

DApper strives to offer the following enhancements:

- Validation is configurable , allowing users to choose whether it is desired, to be avoided, or accepted
- Improved error handling and traceability
- Generalized `addrinfo` and `dnsinfo` structures with associated methods
- Fast-track for common use cases

v1.0
