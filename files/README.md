# files/

Public documents served as static files from the deployed site, for example
`https://asierlopez2003-blip.github.io/files/`. This directory is listed in the
`include:` array of `_config.yml`, which the theme already anticipated, and nothing in
`exclude:` filters PDFs out. Any file here is published verbatim — there is no build step
and no access control.

`_data/documentos.yml` is the index. It is generated from the PDFs in this directory by
`scripts/scan_documents.py`; page counts and file sizes are read from the files
themselves, so the index cannot drift from reality.

## What is published here

This is the complete list. Nothing else in this directory is approved.

| id | File | Document | Language |
|---|---|---|---|
| `master-thesis-desy` | `master-thesis-desy.pdf` | MSc thesis, DESY / Universität Hamburg — triple Higgs couplings in the Real Singlet extension | English |
| `bachelor-thesis-unican` | `bachelor-thesis-unican.pdf` | BSc thesis, Universidad de Cantabria | Spanish |
| `summer-report-cern-nlgad` | `summer-report-cern-nlgad.pdf` | CERN summer student report, nLGAD | English |
| `flipphysics-radiotherapy-ai` | `flipphysics-radiotherapy-ai.pdf` | FlipPhysics Workshop oral presentation — Towards Real-Time High Fidelity Dosimetry (13 slides) | English |

The originals are never modified. These are copies whose PDF metadata has been set
(`/Title`, `/Author`, `/Subject`, `/Keywords`, `/Lang`); the files themselves were not
recompressed.

`Creator` and `Producer` still identify the tool that produced each PDF. They were left
in place rather than stripped.

## Persistent identifiers and provenance

A document may carry a persistent identifier, recorded in `_data/documentos.yml` as
`doi` (the resolver URL, `https://doi.org/...`) and `record_url` (the landing page it
resolves to). Only the CERN report has one so far:

| id | DOI | Repository record |
|---|---|---|
| `summer-report-cern-nlgad` | [`10.17181/mypnp-4wq78`](https://doi.org/10.17181/mypnp-4wq78) | [CERN Document Server](https://repository.cern/records/eybt5-br259) |

Publishing this report was authorised. The copy in this directory is **byte-identical**
to the original handed in at CERN (`md5 7d2651ad6c55820b1bd127b97ce68f9f`, 957481 bytes),
which is in turn the same file the repository serves. The metadata rewrite that produced
the copy published on the site is the only difference and is why its checksum differs:
the published PDF is ~49 KB larger (`md5 3dc5baede0ec6bde6f2b4d6499e137a9`, 1006939 bytes).
If that checksum ever needs to be re-verified, compare against the original path, not
against this copy.

## Naming

The filename *is* the identifier, and it appears in the public URL. Use lowercase
kebab-case, ASCII only, no spaces:

```
bachelor-thesis-unican.pdf        -> /files/bachelor-thesis-unican.pdf
```

Avoid characters that get percent-encoded (`%20` for spaces, `%C3%A9` for accented
letters) and avoid doubling an extension, which is easy to do by dragging a file whose
name already ends in `.pdf`. Neither breaks the build, but both produce URLs that look
broken to a reader.

## Never put anything here that is not already public

This directory is committed to a public repository. Concretely, do not add:

- Identity documents, or anything bearing an ID or passport number
- Signed certificates, contracts, or employment attestations
- Travel documents, tickets, or boarding passes
- Keys, tokens, certificates such as `.p12`/`.pem`, or credential files
- Medical or otherwise personal records
- Any document belonging to someone else — including other people's papers, theses and
  reports, which are easy to accumulate next to one's own work

If a file is added by mistake, deleting it in a later commit removes it from the site but
**not** from the repository's history. Recovery then requires rewriting history. Treat
the first commit of any file here as irreversible, and check before committing.
