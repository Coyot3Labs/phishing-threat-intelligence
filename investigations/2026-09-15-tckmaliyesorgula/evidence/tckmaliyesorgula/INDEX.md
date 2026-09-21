# Screenshot Evidence Index

Original evidence numbering and filenames are retained. English captions describe what each screenshot supports and its limits. The original interface text remains part of the captured evidence.

| No. | Screenshot | Description |
|---|---|---|
| 01 | [urlscan summary](<screenshots/01–urlscan Summary and Live DNS.png>) | Includes a historical scan IP and later Live DNS information. These should not be treated as simultaneous observations. |
| 02 | [Impersonated page](screenshots/02-page-screenshot.png) | Government/e-Devlet appearance and the HTTP-to-HTTPS transition recorded by urlscan. |
| 03 | [HTTP transactions](screenshots/03-http-transactions.png) | Landing page and static resources; no form POST appears in this scan. |
| 04 | [Content analysis](screenshots/04-content-analysis.png) | Government-service wording; no form was found in the DOM of that landing-page scan. |
| 05 | [urlscan indicators](screenshots/05-urlscan-indicators.png) | Domains, IPs and hashes. Presence in this list does not make every entry malicious. |
| 06 | [DNS analysis](screenshots/06-dns-analysis.png) | Cloudflare NS records and an empty answer to the MX query. |
| 07 | [Domain WHOIS](screenshots/07-whois-analysis.png) | Registration time, registrar and nameservers. |
| 08 | [IP WHOIS](screenshots/08-ip-whois.png) | Address allocation and organization metadata; not the operator's physical location. |
| 09 | [Reverse DNS](screenshots/09-reverse-dns.png) | PTR response; not proof of operator identity or ownership. |
| 10 | [HTTP and TLS analysis](screenshots/10-http-tls-analysis.png) | HTTP response and HTTPS connection resets. Last-Modified does not establish the site's launch date. |
| 11 | [TLS handshake failure](screenshots/11-tls-handshake-failure.png) | Negotiation ended without a peer certificate. “Verify return code: 0” does not demonstrate successful TLS in this output. |
| 12 | [Service detection](screenshots/12-nmap-service-detection.png) | Reported HTTP version and tcpwrapped result for port 443. |
| 13 | [Web fingerprint](screenshots/13-whatweb-fingerprint.png) | Server header, page title and tool geolocation label. |
| 14 | [Top-100 port scan](screenshots/14-nmap-top100-services.png) | SSH/HTTP version output; other service guesses were not treated as confirmed services. |
| 15 | [Directory discovery](screenshots/15-gobuster-directory-enumeration.png) | Path status codes and error_log access. A 403 alone does not prove a file exists. |
| 16 | [Historical error log](screenshots/16-public-error-log.png) | PHP errors dated 2023; connection to the current operation was not verified. |
| 17 | [Login form fields](screenshots/17-login-form-fields.png) | Identity/password fields and the login.php form target. |
| 18 | [SMS-code form](screenshots/18-sms-otp-form.png) | A form asking for an SMS code; no real SMS validation is demonstrated. |
| 19 | [Receipt submission code](screenshots/19-receipt-upload-flow.png) | uploade.php target and a success message in the error handler. |
| 20 | [Receipt upload fields](screenshots/20-receipt-upload-fields.png) | File selection. Browser-side file filters do not prove server-side validation. |
| 21 | [Payment routing discovery](screenshots/21-payment-routing-discovery.png) | Payment-pressure wording and page references in client code. |
| 22 | [Card fields and endpoint](screenshots/22-payment-card-api-link.png) | Card number, holder, expiration and security-code fields. |
| 23 | [Card POST code](screenshots/23-card-data-post-flow.png) | Submission to odemeapis.php and response-dependent navigation. |
| 24 | [Payment flow routing](screenshots/24-payment-flow-routing.png) | Client-code links among waiting, error and SMS pages. |
| 25 | [Flow-control code](screenshots/25-bekle-control-routing.png) | Server-response-dependent page selection; researcher egress IP redacted. |
| 26 | [Control endpoint GET response](screenshots/26-datach-get-response.png) | 200 header and no visible GET body; does not validate POST behavior. Egress IP redacted. |
| 27 | [Administrator login HTML](screenshots/27-admin-panel-login.png) | deathfung title artifact and a password field; not evidence of successful login. |
| 28 | [Misleading official link](screenshots/28-burp-misleading-official-link.png) | Official-looking link text points to giris.php. |
| 29 | [Impersonated service list](<screenshots/29 - site.png>) | Government-service appearance served over HTTP. |
| 30 | [Synthetic-data login form](screenshots/30-site.png) | All-zero synthetic identifier and a masked test password. This screenshot alone does not prove a POST occurred. |
| 31 | [Payment demand](screenshots/31-site.png) | TRY 50,000 demand alongside a UYAP claim; not a verified court record. |
| 32 | [Account details and receipt form](screenshots/32-site.png) | IBAN and account holder redacted. The interface does not demonstrate a completed payment. |

[Supplementary Burp observations](notes/burp-observations.md) summarize supplied responses outside this numbered screenshot set.
