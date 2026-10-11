# Evidence Review Log

## Publication Review

- 35 supplied PNG screenshots were reviewed.
- 26 screenshots were selected for publication.
- The selected screenshots did not contain victim credentials, submitted form data, private account details, or the researcher's public egress IP.
- No pixels were altered in the selected publication copies. Their hashes therefore identify byte-for-byte copies of the selected source screenshots.
- Browser and terminal captures preserve the original visible indicators. Written analysis remains defanged.

## Excluded Files

| File | Reason for exclusion |
|---|---|
| `19_urlscan_airbnb_pivot.png` | Same-IP pivot alone did not establish a campaign or actor relationship. |
| `20_urlscan_airbnb_http.png` | Related only through shared hosting; no meaningful content-hash relationship was established. |
| `21_urlscan_airbnb_certificate.png` | Did not support attribution to the Paribu campaign. |
| `23_urlscan_google_ads_impersonation.png` | Same-IP pivot was insufficient to establish a campaign relationship. |
| `23_urlscan_google_ads_impersonation0.png` | Supplemental view of the same unsupported pivot. |
| `24_paribu_subdomain_nxdomain.png` | The image shows an HTTP 502 error from a third-party page, not an authoritative NXDOMAIN result. |
| `26_jamnagar_domain_comparison.png` | Contained visible business contact numbers and was not necessary for the published conclusion. |
| `31_whois_jtcltd.png` | Queried `jtcltd[.]com`, a different domain, and could mislead company attribution. |
| `33_gujarat_directory_ravi_bhadra.png` | Contained a named individual, telephone number, and address; it was unnecessary for the assessment. |

Exclusion means the file was not copied into the public repository. The original local evidence set remains unchanged.
