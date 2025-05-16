# 🔍 Subdomain Scanner (Fast & Multithreaded)

A fast and simple Python-based tool for discovering live subdomains using HTTP and HTTPS checks. Designed for bug bounty hunters, penetration testers, and recon automation.

---

## 📂 Table of Contents

- [📦 Tools & Libraries Used](#-tools--libraries-used)
- [🚧 Challenges Faced](#-challenges-faced)
- [✅ Advantages](#-advantages)
- [⚠️ Disadvantages](#️-disadvantages)
- [💡 Use Cases](#-use-cases)
- [🔮 Future Use & Relevance](#-future-use--relevance)
- [🧪 Sample Output](#-sample-output)
- [📄 Sample Wordlist (`subdomains.txt`)](#-sample-wordlist-subdomainstxt)
- [🛠 How to Run](#-how-to-run)
- [📌 Conclusion](#-conclusion)

---

## 📦 Tools & Libraries Used

| Library/Tool         | Purpose                                       |
|----------------------|-----------------------------------------------|
| `requests`           | Send HTTP/HTTPS requests                      |
| `concurrent.futures` | Run subdomain checks in parallel              |
| `tqdm`               | Display progress bars                         |
| `colorama`           | Add color to console output                   |
| `threading`          | Thread-safe access to shared data             |
| `os`                 | Handle file I/O and output path creation      |

---

## 🚧 Challenges Faced

- Dealing with timeouts and false negatives.
- Skipping complex HTTP redirects and JavaScript-based logic.
- Handling rate-limiting or temporary blocks by CDNs.
- Ensuring safe multi-threaded writes to output data.

---

## ✅ Advantages

- Fast scanning using multithreading.
- Detects both `http://` and `https://` schemes.
- Clear visual feedback with color and progress bar.
- Clean, modular, and readable Python code.

---

## ⚠️ Disadvantages

- Misses some hidden or JavaScript-resolved subdomains.
- Ignores wildcard DNS or DNS-only records.
- No support for subdomain takeover or CNAME detection.
- Cannot follow complex authentication/redirection flows.

---

## 💡 Use Cases

- Bug bounty reconnaissance.
- Penetration testing surface discovery.
- Red team infrastructure mapping.
- Periodic scans for asset monitoring.
- Teaching Python networking and threading.

---

## 🔮 Future Use & Relevance

- Integration with DNS resolvers (like `dnspython`) for better results.
- Add detection for CNAME chains and wildcard DNS.
- Integrate with larger recon frameworks (e.g. recon-ng).
- Add support for subdomain takeover checks.
- Can be extended with service fingerprinting and WAF detection.

---

## 🛠 How To Work

### ✅ Prerequisites

Install required Python libraries:

```bash
pip install requests colorama tqdm threading
```

Environment Setup:

```bash
python -m venv venv # To Create Environment Variable
venv\Scripts\Activate # Activate It
python <file_name>.py # Run The Code
```

Sample subdomain.txt

```bash
www
mail
accounts
support
blog
shop
m
api
dev
vpn
staging
cdn
files
portal
dashboard
beta
test
secure
upload
```

---

## 🧪 Sample Output

```bash
Scanning: 100%|████████████████████████████████| 1000/1000 [00:08<00:00, 115.60it/s]
[+] Discovered: https://mail.example.com
[+] Discovered: http://accounts.example.com
[+] Discovered: https://support.example.com

[✓] Scan complete. Results saved in: discovered_subdomains.txt
```

---

## 📌 Conclusion
This subdomain scanner is a fast, reliable, and extendable tool for subdomain discovery. While simple by design, it serves as a powerful utility for recon workflows, and a great foundation to build more advanced scanners in the future.
