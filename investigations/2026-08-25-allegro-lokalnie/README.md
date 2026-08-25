# Case #001 — Allegro Lokalnie Phishing Infrastructure Analysis

**Analysis Date:** 2026-08-25  
**Threat Type:** Phishing  
**Impersonated Brand:** Allegro Lokalnie  
**Status:** Confirmed Phishing  
**Confidence:** High
## 1. Executive Summary

On 25 August 2026, a phishing domain impersonating Allegro Lokalnie was investigated using OSINT and passive infrastructure analysis.

The observed phishing infrastructure used the domain:

`allegrolokalnie[.]pl-oferta783694[.]biz`

The phishing URL imitated an Allegro Lokalnie product offer. During analysis, the malicious URL redirected visitors to the legitimate Allegro Lokalnie website, indicating that the phishing content was no longer being served at the time of investigation.

The domain was registered shortly before the investigation and used Cloudflare-managed DNS infrastructure.

## 2. Phishing Method

The campaign used brand impersonation and a deceptive domain structure designed to resemble the legitimate Allegro Lokalnie service.

Observed structure:

`allegrolokalnie[.]pl-oferta783694[.]biz`

The legitimate brand name appears at the beginning of the hostname, while the actual registered domain is:

`pl-oferta783694[.]biz`

This structure may cause users to incorrectly interpret `allegrolokalnie.pl` as the real domain.

## 3. Network & Infrastructure Analysis

### DNS

Nameservers:

- `cosmin[.]ns[.]cloudflare[.]com`
- `kiki[.]ns[.]cloudflare[.]com`

Observed A records:

- `104[.]21[.]66[.]103`
- `172[.]67[.]159[.]9`

The IP addresses are associated with Cloudflare infrastructure and therefore should not be treated as confirmed attacker-controlled origin servers.

No MX records were observed.

### TLS Certificate

The phishing hostname presented a Google Trust Services certificate.

- **Issuer:** Google Trust Services
- **Subject:** `CN=pl-oferta783694[.]biz`
- **Valid From:** 2026-08-24
- **Valid Until:** 2026-11-22

The certificate became valid shortly before the investigation.

### Subdomain Enumeration

Passive subdomain enumeration using Subfinder returned no additional known subdomains.

### urlscan.io Analysis

urlscan.io showed the submitted phishing URL redirecting to the legitimate Allegro Lokalnie infrastructure.

No credential or payment-data POST request was observed in the analyzed scan.

Repeated searches did not identify additional campaign URLs associated with the investigated domain.

## 4. Indicators of Compromise

| Type | Indicator |
|---|---|
| Domain | `pl-oferta783694[.]biz` |
| Phishing Hostname | `allegrolokalnie[.]pl-oferta783694[.]biz` |
| IPv4 | `104[.]21[.]66[.]103` |
| IPv4 | `172[.]67[.]159[.]9` |
| Nameserver | `cosmin[.]ns[.]cloudflare[.]com` |
| Nameserver | `kiki[.]ns[.]cloudflare[.]com` |

> **Note:** Cloudflare IP addresses and nameservers represent shared infrastructure and should not independently be treated as malicious IoCs.

## 5. Assessment

The investigated infrastructure is assessed with **high confidence** as phishing infrastructure targeting Allegro Lokalnie users.

Key indicators include:

- deceptive brand-impersonating domain structure;
- very recent domain/certificate activity;
- phishing reporting associated with the investigated URL;
- redirection from the suspicious hostname to the legitimate Allegro Lokalnie service.

At the time of analysis, the phishing content itself was no longer directly observable, limiting analysis of the credential-exfiltration mechanism.

## 6. Tools Used

- urlscan.io
- PhishTank
- WHOIS
- dig
- dnsrecon
- OpenSSL
- Subfinder

## Disclaimer

This investigation was conducted for defensive cybersecurity research and threat-intelligence purposes. No credentials or personal information were submitted to the investigated infrastructure.
