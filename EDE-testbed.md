# EDE testbed

We have created an [EDE](https://www.rfc-editor.org/rfc/rfc8914) testbed at ede.dn5.dk, try to query via <n>.ede.dn5.dk
  
Please see the [IANA Extended DNS Error Codes registry](https://www.iana.org/assignments/dns-parameters/dns-parameters.xhtml#extended-dns-error-codes) for the full list of defined EDE codes.
  
```text
$ dig 16.ede.dn5.dk @ede.dn5.dk

; <<>> DiG 9.18.13-1-Debian <<>> 16.ede.dn5.dk @ede.dn5.dk
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 64722
;; flags: qr rd ad; QUERY: 1, ANSWER: 0, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1500
; EDE: 16 (Censored): (Censored)
;; QUESTION SECTION:
;16.ede.dn5.dk.                 IN      A   

;; Query time: 21 msec
;; SERVER: 194.165.56.50#53(ede.dn5.dk) (UDP)
;; WHEN: Sun May 21 13:48:22 UTC 2023
;; MSG SIZE  rcvd: 56
```
 
