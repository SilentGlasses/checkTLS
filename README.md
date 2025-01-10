# checkTLS
<img width="110" align="left" alt="Padlock" src="https://github.com/user-attachments/assets/22cb79da-64be-4c66-a793-eb2e92229f19" />

**Transport Layer Security** (TLS) is a cornerstone of modern cybersecurity, ensuring secure communication and protecting data from unauthorized access. For organizations, it is not just a technical necessity but a strategic tool for managing risk and maintaining compliance. By understanding and properly managing TLS, businesses can significantly enhance their overall security posture and reduce the likelihood of data breaches or regulatory penalties.

## Why is TLS Important in Risk Management and Security?

TLS plays a critical role in safeguarding sensitive data and maintaining trust in digital communications. Its importance in risk management and security can be summarized as follows:

1. **Mitigates Data Breaches** by protecting sensitive information such as passwords, credit card numbers, and personal details from being intercepted during transmission. Without encryption, attackers can exploit vulnerabilities to access unprotected data.
2. **Prevents Man-in-the-Middle (MITM) Attacks** on both the client and server side, preventing attackers from impersonating a trusted party and intercepting communications. These attacks could lead to data theft or unauthorized access.
3. **Enhances Regulatory Compliance** as many regulations, such as GDPR, HIPAA, and PCI DSS, mandate the use of encryption for securing sensitive data in transit. Implementing TLS helps organizations comply with these requirements, reducing the risk of penalties.
4. **Builds and Maintains Trust** with customers and partners by demonstrating a commitment to protecting their data. This is particularly important for businesses handling financial transactions or personal information.
5. **Reduces Organizational Risk**, reputational damage and financial loss caused by data breaches, cyberattacks, or compliance failures. By encrypting data and verifying identities, TLS reduces the attack surface for cybercriminals.

By transitioning to newer, more robust versions like TLS 1.2 and TLS 1.3, organizations benefit from stronger cryptographic algorithms, improved performance, and enhanced security features that address modern attack vectors. Updating TLS versions also ensures compliance with industry regulations and standards, which increasingly mandate the use of secure protocols.

**Failure to stay current leaves systems exposed to unnecessary risks, jeopardizing both the integrity of communications and the trust of clients and partners**.

## Usage

Using this utility is simple, clone the repo to your computer then use one of the options below. This script can be used on hosts, ips and sites. If a port is not specified, it will default to `443`. The script will generate a logfile as well with the outputs.

- `hostname.domain.com:443`
- `192.168.1.10:443`
- `sitename.com:443`

## Working with the repo

#### Clone the repo:

```
git clone git@github.com:SilentGlasses/check_tls.git
```

#### Option 1 - Pass endpoints on commandline

Use this option when you have one or a few domains to verify.

- To check TLS versions for a single domain:
```
./checkTLS.sh domain:port
```
- To check TLS versions for multiple domains:
```
./checkTLS.sh domain1:port domain2:port
```

#### Option 2 - Pass endpoints in a file

Using the `sites.txt` file when you have lots of domains to check.

- Add your hosts and ports to the `sites.txt` file.
    * One line per host or ip address, like this: `hostname.domain.com:1234` or `000.000.000.000:1234`
- To check TLS versions for domains in a file
```
./checkTLS.sh sites.txt
```

## Results

You should see results like this:

```
Processing provided arguments as domains...
Checking TLS version for: sitename.com:443
  TLS version tls1 is NOT supported on sitename.com:443
  TLS version tls1_1 is NOT supported on sitename.com:443
  TLS version tls1_2 is supported on sitename.com:443
  TLS version tls1_3 is supported on sitename.com:443
-------------------------------------
Error: Cannot resolve domain: sitename1.com
Skipping TLS check for invalid domain: sitename1.com:443
-------------------------------------
```
