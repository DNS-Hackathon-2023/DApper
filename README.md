# DApper — DNS and the Application Layer

DApper is a project that focuses on bridging the gap between available DNS resolver library APIs and application-specific requirements. This project will deliver a problem statement, gap analysis, and a roadmap for future work in the domain of DNS and application integration.

## Supported Platforms

DApper (is supposed to) support the following Opeartion Systems:

- Linux
- BSD
- Windows

## Problem Statement
Current implementations pose potential risks and issues. Up until now, applications have depended on either:


1. `getaddrinfo()` 
   
    Examples: Python, Ruby, and Node’s DNS libraries. use getaddrinfo, as well as Go sometimes.
    This option has various shortcomings, making it less than ideal. 

    One shortcome is that it does not allow the user to provide the details users wants or refine users' search. It's a basic and monolithic entry point, with no DNS-specific knobs. For instance, only A and AAAA queries are supported, which is clearly insufficient.
2. Ad hoc use of DNS resolvers 
   
   Examples: dig.
   
   The option could be risky without developers' expertise in DNS.

which are both more or less problematic. 


## Components

The key components of DApper include:

- DNSSEC (Domain Name System Security Extensions)
- Local cache (e.g., Windows DNS Client service)
- Routability
- Reachability
- IPv4/IPv6 dual stack
- Happy Eyeballs algorithm
- Various DNS records, such as A/AAAA, HTTPS/SVCB, TXT, SRV, URL, and TLSA

## Goals

The primary goals of the DApper project are:

- Develop an EDE (Extended DNS Errors) testbench
- Draft problem statements
- Conduct an application gap analysis

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