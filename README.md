# forms

Source court-form PDFs used by **FilingFoundry** for LLM-driven intake and structured form assembly. This repo exists so the build pipeline can pull canonical, unmodified source PDFs via `git clone` (the originating court sites are not directly reachable from the build sandbox).

> These are official forms published by the respective courts. They are stored here verbatim as source-of-truth inputs. No legal advice is offered or implied.

## Jurisdictions

### Arizona — Superior Court of Maricopa County
Summary Consent Decree process for divorce of a non-covenant marriage.

| File | Form | Use |
|------|------|-----|
| `drdsc1z.pdf` | DRDSC1 (5606) | Summary consent decree — **with** minor children |
| `drdsa1z.pdf` | DRDSA1 (5610) | Summary consent decree — **no** children |

### Florida — Supreme Court Approved Family Law Forms
The `12.9xx` / `9xx` series of dissolution-of-marriage forms and instructions (petitions, financial affidavit, marital settlement, consent decree packets, etc.). Files suffixed `ADA` are the accessible/tagged versions.

| File | Form |
|------|------|
| `12.901a.pdf` | 12.901(a) Petition — simplified dissolution |
| `12.901(b)(2) ADA.pdf` | 12.901(b)(2) Petition — no dependent/minor children |
| `901b1.pdf` | Instructions — 12.901(b)(1), with dependent/minor children |
| `901b3.pdf` | 12.901(b)(3) |
| `12.902(d) ADA.pdf` | 12.902(d) Marital settlement |
| `12.902(i) ADA.pdf` | 12.902(i) |
| `12.902(j) ADA.pdf` | 12.902(j) |
| `12.902e.pdf` | 12.902(e) Child support guidelines worksheet |
| `12.902k.pdf` | 12.902(k) |
| `902b10-21.pdf`, `902f1.pdf`, `902f2.pdf` | 12.902 financial affidavit series |
| `FINANCIAL AFFIDAVIT_LONG FORM.pdf` | 12.902(c) Financial affidavit (long form) |
| `12.913(a)(1) ADA.pdf`, `913b.pdf` | 12.913 |
| `915 8.25.23.pdf` | 12.915 |
| `12.928 ADA.pdf` | 12.928 Cover sheet |
| `903a.pdf`, `903b.pdf`, `903c1.pdf`, `903c2.pdf` | 12.903 final judgment series |
| `995a.pdf` | 12.995(a) Parenting plan |
| `12.990(a) ADA.pdf`, `990b1.pdf`, `990b2.pdf`, `990b3.pdf` | 12.990 final judgment of dissolution |

### Derived / packaged
| File | Description |
|------|-------------|
| `summary_consent_decree_packet_with_children.pdf` | Assembled packet — with children |
| `summary_consent_decree_packet_without_children.pdf` | Assembled packet — no children |
| `filingfoundry_notary_docs.zip` | Notary document bundle |

## Conventions

- Files are stored **verbatim** as published. Do not re-save, flatten, or re-export — downstream extraction relies on the original field structure and tags.
- `*z.pdf` = Arizona Maricopa source forms; `*ADA*` = Florida accessible versions.
- This repo is data-only. Pipeline code lives in the FilingFoundry project.

## Usage

```bash
git clone https://github.com/kforkarim/forms.git
```

The intake pipeline reads these PDFs as the canonical templates for field extraction and structured JSON form assembly.
