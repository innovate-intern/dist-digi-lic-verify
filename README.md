
# Experimental Implementation of Distributed Digital Driver License Verification

This project demonstrates a **proof-of-concept implementation** of a **distributed system** for secure **digital driver license verification** using public-key cryptography. It simulates the process where a client (driver) can present a digitally signed license to an authority for verification in a secure and tamper-proof manner.

---

## 📌 Project Objectives

- Simulate a digital driver license system where licenses are signed by a central authority.
- Implement secure verification of licenses using public/private key encryption.
- Demonstrate the distributed nature by separating roles: **Issuer**, **Holder**, and **Verifier**.
- Provide CLI-based encryption, signing, and validation operations using OpenSSL.

---

## 🧩 Project Structure

```
NS_A4/
├── CA/
│   ├── private/
│   ├── certs/
│   ├── newcerts/
│   ├── index.txt
│   ├── openssl.cnf
│   └── ... (CA configuration and setup files)
├── client/
│   ├── license_request.txt
│   ├── client_key.pem
│   ├── client_cert.pem
│   └── ... (client-side license generation and signing)
├── verifier/
│   ├── license.txt
│   ├── verify.sh
│   └── ... (scripts to verify license authenticity)
├── generate_ca.sh
├── generate_license.sh
└── README.md
```

---

## 🔐 Cryptographic Workflow

1. **Certificate Authority (CA)**:
   - Generates a root certificate and private key.
   - Signs digital license requests from clients.

2. **Client (Driver)**:
   - Generates a key pair.
   - Requests license signing from the CA.
   - Stores the signed license.

3. **Verifier (Authority)**:
   - Uses the CA’s public certificate to verify the authenticity of the presented license.

---

## 🛠️ How to Run

### 1. Setup Certificate Authority (CA)
```bash
cd NS_A4/CA
./generate_ca.sh
```

### 2. Generate and Sign a Digital License
```bash
cd NS_A4/client
./generate_license.sh
```

### 3. Verify the License
```bash
cd NS_A4/verifier
./verify.sh
```

Ensure that all certificate paths and config files are correctly set in each script.

---

## 📚 Dependencies

- [OpenSSL](https://www.openssl.org/) – Required for certificate generation and verification
- Bash (for running shell scripts)

Install OpenSSL using:
```bash
sudo apt install openssl
```

---

## 📄 Sample License Content

Example output of a digitally signed license:
```
Driver Name: John Doe
License No: DL-123456789
Issue Date: 2024-01-01
Expiry Date: 2034-01-01
Signature: <Base64 encoded signature>
```

---

## ✅ Verification Output

Example of a successful verification:
```
License verified successfully.
Issuer: Trusted Certificate Authority
Valid: Yes
```

---

## 🔍 Use Cases

- Government digital identity and license platforms
- Secure offline license verification systems
- IoT-enabled driver ID systems
- Blockchain-ready license verification layers

---

## 📌 Notes

- This is a **simulated environment** and **not intended for production use**.
- Focus is on understanding and demonstrating **PKI concepts** and **distributed verification**.

---

## 👨‍💻 Author

**Dushyant**  
GitHub: [@dushyant18033](https://github.com/dushyant18033)

---

## 📜 License

This project is released under the [MIT License](https://opensource.org/licenses/MIT).
