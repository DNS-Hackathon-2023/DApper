# DApper — DNS and the Application Layer

DApper is a project that focuses on bridging the gap between available DNS resolver library APIs and application-specific requirements. This project will deliver a problem statement, gap analysis, and a roadmap for future work in the domain of DNS and application integration.

## Supported Platforms

DApper (is supposed to) support the following Opeartion Systems:

- Linux
- BSD
- Windows

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

## Application Statement

DApper addresses two primary use cases:

1. The `getaddrinfo()` function
2. Ad hoc usage of DNS resolvers

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