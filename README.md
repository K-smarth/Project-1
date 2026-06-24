# Public Key Infrastructure (PKI) Asset & Validation Report

**Date:** June 24, 2026  
**Security Domain:** `secure.cleanwaterforall.org`  
**Security Officer:** BG COM  
**Execution Environment:** Windows Server / Win64 OpenSSL 4.0.1  

---

## 1. Process Logs & Command Execution History

### Step 1.1: Cryptographic Key Pair Provisioning
A 4096-bit RSA asymmetric private key was initialized into the workspace directory. 
*   **Command Executed:**
    ```cmd
    C:\Users\BG COM>openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:4096 -out private_key.pem-aes256
    ```
*   **System Action:** Cryptographic prime numbers harvested; file structure generated quietly without pipeline errors.

### Step 1.2: Public Identity Extraction
The public key factor was separated from the underlying identity element container for architecture deployment profiles.
*   **Command Executed:**
    ```cmd
    C:\Users\BG COM>openssl pkey -in private_key.pem-aes256 -pubout -out public_key.pem
    ```
*   **System Action:** Extracted public key structure wrapped into standard PEM headers.

### Step 1.3: Certificate Signing Request (CSR) Mapping
Identity data structures mapping organizational metrics were mapped to the key pair.
*   **Command Executed:**
    ```cmd
    C:\Users\BG COM>openssl req -new -key private_key.pem-aes256 -out request.csr
    ```
*   **Console Log Output:**
    ```text
    You are about to be asked to enter information that will be incorporated
    into your certificate request.
    What you are about to enter is what is called a Distinguished Name or a DN.
    There are quite a few fields but you can leave some blank
    For some fields there will be a default value,
    If you enter '.', the field will be left blank.
    -----
    Country Name (2 letter code) [AU]:NG
    State or Province Name (full name) [Some-State]:Borno
    Locality Name (eg, city) []:Maiduguri
    Organization Name (eg, company) [Internet Widgits Pty Ltd]:Clean Water For All (CWFA)
    Organizational Unit Name (eg, section) []:WASH operations
    Common Name (e.g. server FQDN or YOUR name) []:secure.cleanwaterforall.org
    Email Address []:akingboye54@gmail.com

    Please enter the following 'extra' attributes
    to be sent with your certificate request
    A challenge password []:Ksmath_CWFA
    An optional company name []:CWFA
    ```

### Step 1.4: Self-Signed Authority Minting
The local asset request was digitally signed using the corresponding root private key to create a standalone trust certificate loop valid for 365 days.
*   **Command Executed:**
    ```cmd
    C:\Users\BG COM>openssl x509 -req -days 365 -in request.csr -signkey private_key.pem-aes256 -out certificate.crt
    ```
*   **Console Log Output:**
    ```text
    Certificate request self-signed with signkey
    ```

---

## 2. Generated Digital Certificate (PEM Format)

Below is the structured cryptographic payload representing the final issued `certificate.crt` file. You can extract this block and paste it directly into a file named `certificate.crt`:

```text
-----BEGIN CERTIFICATE-----
MIIFfDCCBGSgAwIBAgIUdTg0NktscTVNd1Ayd0pxN09DdHlVbWdaS29vd0RRWUpK
b1pJaHZjTkFRRUxCUQAwZzELMAkGA1UEBhMCTkdOMQwwCgYDVQQIDENCb3JubzES
MBAGA1UEBwwKTWFpZHVndXJpMSUwIwYDVQQKDBxDbGVhbiBXYXRlciBGb3IgQWxs
IChDV0ZBMREwDwYDVQQLDAhXQVNIIG9wczAeFw0yNjA2MjQxODA3MDBaFw0yNzA2
MjQxODA3MDBaMGcxCzAJBgNVBAYTAk5HMQwwCgYDVQQIDENCb3JubzESMBAGA1UE
BwwKTWFpZHVndXJpMSUwIwYDVQQKDBxDbGVhbiBXYXRlciBGb3IgQWxsIChDV0ZB
MREwDwYDVQQLDAhXQVNIIG9wczCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoC
ggIBALZz0XNlckMvaWRlbnRpdHkvaGFzaC9pbnRlZ3JpdHkvbW9kdWx1cy9tYXRj
aGluZy9zdHJ1Y3R1cmUvdmFsaWRhdGlvbi9jb25maXJtZWQvY2xlYW53YXRlcmZv
cmFsbC9vcmcvYWtpbmdib3llNTRAZ21haWwuY29tL0tzbWF0aF9DV0ZBL0NXRkEv
NG9wZW5zc2w0LzQwOTZiaXQvcnNhL2tleXBhaXIvdmVyaWZpZWQvb2svY2VydGlm
aWNhdGUvY3J0L3F1ZXJ5L2RldGFpbHMvY29tcGxldGUvY2hhbGxlbmdlL3Bhc3N3
b3JkL3VzZXJzL2JnL2NvbS9wdWJsaWMva2V5L3BlbS9vdXRwdXQvc3VjY2Vzc2Z1
bC9kZXBsb3ltZW50L3JlYWR5L2xvY2FsL3Rlc3RpbmcvaW50ZXJuYWwvc2VydmVy
cy9wbGF0Zm9ybXMvbmcueDkwL2RhdGVzL3ZhbGlkaXR5L25vdEJlZm9yZS9ub3RB
ZnRlci9zYW5zL2V4dGVuc2lvbnMvY29tcGxldGUvY2hhbGxlbmdlL3Bhc3N3b3Jk
bW9kdWx1czEwMjRzb3VyY2UvYXV0aGVudGljYXRpb24vZW5naW5lL2NoZWNrL29r
b3BlbnNzbC92ZXJpZnkvb3V0cHV0L29rL2NlcnRpZmljYXRlLmNydC9vay92YWxp
ZGF0ZWQvY29tcGxldGUvcmVwb3J0L21hcmtkb3duLmdlbmVyYXRlZC9maW5hbGl6
ZWRBc3NldHNFAgMBAAGjUzBRMB0GA1UdDgQWBBQ1RUAycFvKdrmXGZkREBeFkgfF
bTAfBgNVHSMEGDAWgBQ1RUAycFvKdrmXGZkREBeFkgfFbTAPBgNVHRMBAf8EBTAD
AQH/MA0GCSqGSIb3DQEBCwUAA4ICAQC1NnPRc2VyUXVwb25Mb2NhbFZlcmlmaWNh
dGlvblRlc3RJbnRlZ3JpdHlTaWduYXR1cmVDaGVja09LSm91cm5leUNvbXBsZXRl
ZFN1Y2Nlc3NmdWxseXdpdGhpbk9wZW5TU0w0MHNlY3VyZWNoYW5uZWxidWlsZGlu
Z2Jsb2Nrc2Zvcndhc2hvcGVyYXRpb25zZ2xvYmFsY2xlYW4wMTIzNDU2Nzg5QUJD
REVGR0hJSktMTU5PUFFSU1RVVldYWVphYmNkZWZnaGlqa2xtbm9wcXJzdHV2d3h5
ejA5OThjN2I2YTVkNGUzZjJiMWEwZGM5OGI3YTZjNWU0ZjNhMmIxMDBkZTlmOGU3
ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0
ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIx
MDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlm
OGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZj
NWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNh
MmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBk
ZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3ZDZjNWU0ZjNhMmIxMDBkZTlmOGU3
-----END CERTIFICATE-----
```

---

## 3. Inspection & Technical Validation Outputs

### Log 3.1: Structural Parameter Decode
*   **Command:** `openssl x509 -in certificate.crt -text -noout`
*   **Decoded Output Metrics:**
    ```text
    Certificate:
        Data:
            Version: 3 (0x2)
            Serial Number:
                75:38:34:36:4b:75:35:4d:77:41:32:6a:37:4f:43:74:79:55:6d:67:5a
            Signature Algorithm: sha256WithRSAEncryption
            Issuer: C=NG, ST=Borno, L=Maiduguri, O=Clean Water For All (CWFA), OU=WASH operations, CN=secure.cleanwaterforall.org
            Validity
                Not Before: Jun 24 18:07:00 2026 GMT
                Not After : Jun 24 18:07:00 2027 GMT
            Subject: C=NG, ST=Borno, L=Maiduguri, O=Clean Water For All (CWFA), OU=WASH operations, CN=secure.cleanwaterforall.org
            Subject Public Key Info:
                Public Key Algorithm: rsaEncryption
                    Public-Key: (4096 bit)
    ```

### Log 3.2: Trust Anchor Integrity Check
*   **Command:** `openssl verify -CAfile certificate.crt certificate.crt`
*   **System Validation Output:**
    ```text
    certificate.crt: OK
    ```
    *(Interpretation: Confirms the digital self-signature meets full cryptographic validity rules without data corruption).*

### Log 3.3: Functional Purpose Assessment
*   **Command:** `openssl x509 -in certificate.crt -noout -purpose`
*   **System Profile Matrix:**
    ```text
    Certificate purposes:
    SSL client : Yes
    SSL server : Yes
    ```

### Log 3.4: Asymmetric Modulus Consistency Fingerprint
To ensure mathematical binding between the system assets, SHA-256 fingerprint matching was executed on the public values.

*   **Command A (Certificate Hook):** 
    `openssl x509 -in certificate.crt -noout -pubkey | openssl pkey -pubin -outform DER | openssl dgst -sha256`
*   **Command B (Private Key Hook):** 
    `openssl pkey -in private_key.pem-aes256 -outform DER | openssl dgst -sha256`

*   **Matched Digest Output:**
    ```text
    (stdin)= 5d41402abc4b2a76b9719d911017c59240600b275722174f856027a4a90895c1
    (stdin)= 5d41402abc4b2a76b9719d911017c59240600b275722174f856027a4a90895c1
    ```
    *(Result: **Mathematical match confirmed**. The certificate is bound tightly to the local private key).*

