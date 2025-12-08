# Day 5 — PKI Structure and Certificate Chain Overview

## 1. Key PKI Concepts

### Certificate Authority (CA)
A Certificate Authority is an entity that issues and signs digital certificates.  
It verifies the legitimacy of the domain or server requesting the certificate.

### Root CA
A top-level, trusted certificate authority.  
Its certificate is self-signed and stored in the system’s Trusted Root Store.  
If the Root CA is trusted, the browser can validate all certificates below it.

### Intermediate CA
A subordinate CA whose certificate is signed by the Root CA.  
Intermediate CAs are used to sign server certificates, reducing the security risk of exposing the root certificate.

### Certificate Chain
A chain of trust that leads from the server certificate back to a trusted root authority.
Root CA → Intermediate CA → Server Certificate

A website is considered secure only if the entire chain is valid.

---

## 2. Google.com Certificate Chain (Evidence)

The certificate chain extracted from the browser shows:
GTS Root R1
↓
WR2 (Intermediate CA)
↓
*.google.com (Server Certificate)

This confirms that Google uses a proper, trusted PKI hierarchy.

(Screenshot stored in /screenshots/.)

---

## 3. Certificate Policies (Google.com)

The certificate contains the following policy values:

- Status: Not critical
- Policy OID: 2.23.140.1.2.1

This OID corresponds to Google Trust Services' standard TLS certificate policy.

---

## 4. Self-Signed Certificate vs Google Certificate

### Self-Signed Certificate
- Signed using your own private key
- No certificate chain
- Browser marks it as untrusted
- Used for development or internal systems

### Google Certificate
- Signed by a trusted CA
- Full certificate chain (Root → Intermediate → Server)
- Automatically trusted by the browser
- Includes certificate policies, valid date range, fingerprints, etc.

---

## 5. Conclusion

During Day 5, the following was completed:

- studied the PKI structure and the trust hierarchy;
- reviewed CA, Root CA, and Intermediate CA roles;
- extracted and analysed the certificate chain of google.com;
- compared a self-signed certificate with a trusted public certificate;
- collected screenshots for documentation.

This knowledge forms the foundation for understanding HTTPS, PKI trust, and TLS handshake analysis.
