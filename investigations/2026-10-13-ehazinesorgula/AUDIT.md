# CASE002 — Concise evidence audit

**Audit date:** 24 October 2026. Source: `CASE002_evidence.zip`. Review was offline; no new connections to targets were made. The original ZIP and existing project references were left unchanged.

## Scope and duplicates

- **35 files:** 27 PNG, 7 TXT, 1 HAR (network capture). SHA-256 comparison identified **32 unique byte contents**. No files were empty; ZIP entries were read to check integrity.
- E08/E30/E32/E34 are four copies of the same 18,469-byte JavaScript file: three extra copies. SHA-256: `4bd72a1646f398124fd9be11437a6b85719e422bbfab63bff6a4239f3ba7bdc7`. Domain labels were retained; they do not establish independent provenance.
- E06 is a browser **view-source** HTML wrapper. Extracting the displayed source, decoding HTML entities and normalizing whitespace produces a match with E07. Their bytes differ; they cannot be counted as two independent acquisitions.
- E31/E33/E35 are overlapping screenshots extending the same local hash comparison to two, three and four files. They are not multiple independent confirmations.
- Filename prefixes cover 01–32; 12 occurs twice and 13 three times. No prefix is missing, but this does not establish completeness of collection. Unique E01–E35 identifiers prevent ambiguity.

## Sensitive data and publication decision

| Evidence | Sensitivity |
|---|---|
| E10 | Plaintext password, Turkish national ID-shaped values and a person's name. Treated as sensitive because their status as test data could not be verified. |
| E11, E13, E15, E17 | API access secret/query parameters; names, phone and bank/IBAN details. The **background** behind the transparent terminal in E13/E15/E17 also exposes data. |
| E26–E27 | Payment session context; E26 contains an exposed payment token and wallet address. |
| E03, E06–E09, E30, E32, E34 | Analytics/page identifiers, local data fields or default address/person templates. Static templates are not verified victim records. |
| Other PNG files | Raw network addresses; some images contain analyst username/host/directory, browser environment or unnecessary registration/contact details. |

**Decision:** None of the 35 raw files is included in the publication package. Findings are described without copying sensitive values; URL/domain/IP indicators are defanged. Originals and local working copies were retained. A Git exclusion rule was added for the working directory; that directory must not be shared separately.

## Technical conclusions

1. Institution impersonation and a login flow collecting identity/password fields are strongly supported. E10 shows the POST, but not its server response body or real user authentication.
2. Both POSTs among the HAR's 20 requests are telemetry; the credential POST is absent from the HAR. The JavaScript response in E09/5 matches E08 byte for byte.
3. E11 configures an external API relationship. E14 is an application error inside HTTP 200, not a successful identity lookup.
4. Cloudflare IP/ASN information does not identify the origin server or a common operator. E17/E18 DNS results require caution because their time/domain-spelling context is incomplete.
5. The last observed payment state is `pending`. A transfer, victim payment or phishing revenue is not established.

## Gaps and priority

| Priority | Missing evidence / impact |
|---|---|
| High | No complete request/response capture with sensitive values removed for the credential POST or external API transfer; no proxy server code. Successful end-to-end transfer cannot be verified. |
| High | No scan UUID, UTC acquisition time, original URL and independently acquired hashed response for every candidate domain. Deployment across four domains and a common operator cannot be established. |
| Medium | No complete urlscan[.]io JSON export, raw DNS/WHOIS/TLS records, certificate files or collection log. E23's filename mentions DNS, but the image contains only WHOIS. |
| Medium | No earlier transformation log for E06→E07; equivalence was rechecked in this audit. Relative search ages and ZIP/file timestamps were not treated as reliable event times. |
| Outside scope | No evidence establishes the initial delivery message, victim count, successful payment/on-chain transaction, operator identity or current availability. |

Any follow-up collection should use an isolated analysis environment; copies prepared for sharing require another secret/PII review.

**Source ZIP:** 2,689,056 bytes; total extracted file size: 3,259,383 bytes. SHA-256: `e1e2ec24a2e255d9c0dbfb2cf40487498057cee561ba5be91692387e768f6f12`.

**Publication package:** This English text/CSV release contains only derived findings. Detailed decisions for all 35 files are in [evidence_index.csv](evidence_index.csv). SHA-256 identifies the bytes received for this audit; it does not by itself authenticate their historical acquisition.
