### Day 4 — HTTP Headers (Completed)

Commands:
- curl -v http://example.com
- curl -v http://httpbin.org/get
- curl -v https://example.com

Findings:
- User-Agent: curl/7.81.0
- Host: example.com
- Server: awselb/2.0 (from httpbin.org)
- TLS version: TLSv1.3
- Cipher suite: TLS_AES_256_GCM_SHA384
- Certificate CN: *.example.com (issued by DigiCert Global G3 TLS ECC SHA384 2020 CA1)

Summary:
HTTP transfers data in plain text, allowing visibility of headers and content.  
HTTPS encrypts all communication using TLS, ensuring privacy and authenticity.  
Captured and verified via curl -v output and Wireshark TLS handshake traces.
