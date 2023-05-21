# Brainstorming

## Goals

The primary goals of the DApper project are:

- Develop an EDE (Extended DNS Errors) testbench
- Draft problem statements
- Conduct an application gap analysis
- Consider a possible future Internet draft entitled 
  "Getaddrinfo() considered harmful"

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

The use described above gives rise to a number of problems.

1.  The `getaddrinfo()` function does not indicate the valid lifetime
    (TTL) of the address data it provides to the application. On the other
    hand, some hostnames represent a constellation of replicas of the same
    content, among which load is balanced using the DNS; in such a case,
    the TTL announced in the DNS is typically very short. Any mismatch
    between the respective timers used by the application's cache managemnt
    strategy and the content providers load-balancing strategy may
    frustrate the intent of both parties.

2.  Some popular resolver libraries support a very limited repertoire
    of DNS QTYPEs, and lack support for Handling of Unknown DNS Resource
    Record (RR) Types as specified in RFC3597.

3.  Failures in processing a DNS request are poorly, if at all, exposed
    to the application, which therefore has little opportunity for
    sophisticated error recovery.  Extended DNS Error codes, as specified
    RFC8914, are usually not exposed at all.

## Features which should not be lost in any solution

- RFC8914: Extended DNS Error codes
- RFC6724: IPv6 Address selection
- Support for alternative namespaces (*/etc/hosts*, NSS, etc)
- DNSSEC (Domain Name System Security Extensions)
- Local cache (e.g., Windows DNS Client service)
- Routability
- Reachability
- IPv4/IPv6 dual stack
- Happy Eyeballs algorithm
- DNS records other than A/AAAA, eg. HTTPS/SVCB, TXT, SRV, URL, TLSA

## Resources

DApper needs to identify resources from Windows, BSD, and Linux/GNU libraries.

## Application Expectations & Enhancements

### Expectations

Features expected (or even performed) by existing applications should continue
to be available; examples of such features include:

- Returning an `addrinfo` chain or simply a connection handle
- Overhead amortization, e.g., in-app cache
- Access to auxiliary records using ad hoc code
- Asynchronous operation and thread-safety

### Enhancements

DApper aims to identify enhanced featured which applications should
come to expect from a DNS library, such as:

- DNSSEC validation is configurable , allowing users to choose
  whether it is desired, to be avoided, or accepted;
- Improved error handling and traceability;
- Generalized `addrinfo` and `dnsinfo` structures with associated methods;
- Fast-track for common use cases;

v1.1
