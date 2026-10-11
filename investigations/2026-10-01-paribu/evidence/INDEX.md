# Evidence Index

This directory contains 26 publication copies selected from the original CASE-001 evidence set. The screenshots document the observed phishing page, urlscan.io results, passive DNS and WHOIS checks, TLS certificate evidence, and the parent-domain identity review.

Screenshots preserve the captured interface and therefore contain active-looking domains, URLs, and IP addresses. Treat all displayed indicators as untrusted and do not visit them directly.

| File | Evidence role | Report section | Notes |
|---|---|---|---|
| [01_urlscan_summary.png](screenshots/01_urlscan_summary.png) | urlscan.io scan summary | Executive Summary | Shows the phishing hostname, observed IP, ASN, request count, and scan time. |
| [02_urlscan_screenshot.png](screenshots/02_urlscan_screenshot.png) | Captured phishing landing page | Phishing Method | Shows the Paribu-branded clone rendered by urlscan.io. |
| [03_urlscan_http.png](screenshots/03_urlscan_http.png) | HTTP transaction list | HTTP Observations | Shows 64 HTTP transactions and same-host resources. |
| [04_urlscan_dom.png](screenshots/04_urlscan_dom.png) | DOM access limitation | HTTP Observations | Documents that raw DOM access was unavailable without authentication. |
| [05_urlscan_indicators.png](screenshots/05_urlscan_indicators.png) | Resource hashes | Content Comparison | Shows urlscan.io indicators derived from page resources. |
| [06_urlscan_content.png](screenshots/06_urlscan_content.png) | Form analysis | Phishing Method | Shows the only form identified on the landing page. |
| [07_urlscan_content_api.png](screenshots/07_urlscan_content_api.png) | Copied Paribu API documentation text | Content Comparison | The displayed official API examples are static page content, not observed POST traffic. |
| [08_kali_dig.png](screenshots/08_kali_dig.png) | Historical A record | Network and TLS Infrastructure | Shows the phishing hostname resolving to `192[.]227[.]177[.]140`. |
| [09_kali_dig_root_domain.png](screenshots/09_kali_dig_root_domain.png) | Parent-domain A records | Network and TLS Infrastructure | Shows the Cloudflare addresses used by the parent domain. |
| [10_kali_whois_ip.png](screenshots/10_kali_whois_ip.png) | IP WHOIS | Network and TLS Infrastructure | Shows the registered address block and hosting organization data. |
| [11_kali_asn_cymru.png](screenshots/11_kali_asn_cymru.png) | Team Cymru ASN lookup | Network and TLS Infrastructure | Corroborates AS36352 for the observed IP. |
| [12_kali_reverse_dns.png](screenshots/12_kali_reverse_dns.png) | Reverse DNS | Network and TLS Infrastructure | Shows the PTR result `srv1[.]uwblue[.]com`. |
| [13_kali_ptr_forward_check.png](screenshots/13_kali_ptr_forward_check.png) | PTR forward check | Network and TLS Infrastructure | Shows that the PTR hostname resolved to a different address; it is not ownership proof. |
| [13_kali_whois_root_domain.png](screenshots/13_kali_whois_root_domain.png) | Parent-domain WHOIS | Company Identity Assessment | Shows registration dates, registrar, and nameservers. |
| [14_kali_subfinder.png](screenshots/14_kali_subfinder.png) | Passive subdomain enumeration | Network and TLS Infrastructure | Shows the observed parent and Paribu-related subdomains. |
| [15_kali_dns_comparison.png](screenshots/15_kali_dns_comparison.png) | DNS comparison | Network and TLS Infrastructure | Compares the parent-domain and phishing-hostname answers. |
| [16_kali_dns_nxdomain.png](screenshots/16_kali_dns_nxdomain.png) | NXDOMAIN observation | Timeline | Shows the phishing hostname returning NXDOMAIN on October 5, 2026. |
| [17_urlscan_historical_search.png](screenshots/17_urlscan_historical_search.png) | urlscan.io history | Timeline | Shows one public scan result for the phishing hostname at capture time. |
| [18_urlscan_ip_pivot.png](screenshots/18_urlscan_ip_pivot.png) | Shared-IP pivot | Confidence Assessment | Demonstrates unrelated-looking domains on the same address and supports the caution against IP-only attribution. |
| [22_urlscan_paribu_certificate.png](screenshots/22_urlscan_paribu_certificate.png) | urlscan.io certificate view | Network and TLS Infrastructure | Shows the phishing certificate subject and validity dates. |
| [25_jamnagar_official_website.png](screenshots/25_jamnagar_official_website.png) | Parent-domain website | Company Identity Assessment | Documents the transport-company content associated with the parent domain. |
| [26_certspotter_paribu_subdomain.png](screenshots/26_certspotter_paribu_subdomain.png) | Certificate Transparency query | Network and TLS Infrastructure | Shows the phishing hostname in Certificate Transparency data. |
| [27_certspotter_paribu_certificate_dates.png](screenshots/27_certspotter_paribu_certificate_dates.png) | Certificate dates | Timeline | Shows the certificate validity timestamps and non-revoked status returned by the source. |
| [28_censys_paribu_certificate.png](screenshots/28_censys_paribu_certificate.png) | Censys certificate search | Network and TLS Infrastructure | Corroborates the certificate subject and validity window. |
| [29_censys_paribu_certificate_details.png](screenshots/29_censys_paribu_certificate_details.png) | Censys certificate details | Network and TLS Infrastructure | Shows issuer, validity, trust status, and fingerprint view. |
| [30_whois_jamnagartransportco.png](screenshots/30_whois_jamnagartransportco.png) | Parent-domain WHOIS verification | Company Identity Assessment | Confirms the parent-domain registration timeline and Cloudflare nameservers. |

The filenames in [SHA256SUMS.txt](../SHA256SUMS.txt) are relative to `evidence/screenshots/`.

See [REVIEW_LOG.md](REVIEW_LOG.md) for the publication review and excluded files.
