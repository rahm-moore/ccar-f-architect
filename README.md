# Training & Certification Scaffold

Personal training-objective tracker for professional development as a Data Architect.
Covers all training sources — not just Anthropic certifications — with a consistent
structure so a new provider (a new Udemy course, a new Adobe cert, etc.) drops in
without reorganizing everything else.

## How this repo is organized

```
programs/               One folder per training provider/track
  anthropic-ccar/        Claude Certified Architect (Foundations + Professional)
  udemy/                 Udemy courses
  linkedin-learning/     LinkedIn Learning courses
  adobe/                 Adobe certifications/training
  <new-provider>/        Copy templates/program-README-template.md to start one
certificates/            Master registry of earned certificates, linking out to
                          the actual certificate files stored in Google Drive
templates/                Reusable templates for adding a new program or module
```

Each program folder follows the same shape:
- `README.md` — what the program is, status, links to the provider's course catalog
- `study-progress.md` — course/module tracker (see template)
- `notes.md` — running notes by module/topic
- `resources.md` — links, official vs. third-party flagged
- `practice-tests/` — optional, if the program benefits from self-testing

## Active programs

| Program | Status | Folder |
|---|---|---|
| Claude Certified Architect (Anthropic) | Active — see its README for F/P pivot history | [`programs/anthropic-ccar/`](programs/anthropic-ccar/) |
| Udemy | Not yet started | [`programs/udemy/`](programs/udemy/) |
| LinkedIn Learning | Not yet started | [`programs/linkedin-learning/`](programs/linkedin-learning/) |
| Adobe | Not yet started | [`programs/adobe/`](programs/adobe/) |

## Certificates

All earned certificates are logged in [`certificates/certificates.md`](certificates/certificates.md),
which links out to the certificate files kept in Google Drive (this repo does not store
the certificate files themselves — just pointers to them).

## Adding a new training program

1. Copy `templates/program-README-template.md` into a new `programs/<provider-name>/README.md`.
2. Copy `templates/study-progress-template.md` into `programs/<provider-name>/study-progress.md`.
3. Add a row to the **Active programs** table above.
4. When a course/module completes and a certificate is issued, add a row to
   `certificates/certificates.md` and upload the certificate to Google Drive.
