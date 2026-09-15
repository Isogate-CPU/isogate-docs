# Isogate documentation

Public, implementation-free documentation for
[Isogate](https://isogate.tech), an inspectable deterministic computing
ecosystem.

The [complete product and contract documentation](docs/Isogate-Complete-Documentation.md)
is the canonical reference for this repository. The focused pages provide
navigation and context:

- [Documentation home](docs/index.md)
- [Architecture](docs/architecture.md)
- [Security and trust boundaries](docs/security.md)
- [Contract references](docs/contracts.md)
- [Version compatibility](docs/compatibility.md)
- [Official links](docs/links.md)

This repository intentionally contains documentation only. It does not contain
application implementation, smart-contract source, generated PDFs, deployment
artifacts, credentials, or private operational data.

## Local documentation site

The site is configured in [`mkdocs.yml`](mkdocs.yml). To preview it locally
without committing generated output:

```bash
python3 -m venv .venv
. .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install "mkdocs==1.6.1"
mkdocs serve
```

Open the local URL printed by MkDocs. To perform the same static build used by
continuous integration:

```bash
mkdocs build --strict --site-dir site
```

The generated `site/` directory is ignored by Git. No credentials or network
services are required to build the documentation.

## Governance and contributions

Documentation is maintained through reviewed pull requests. Contributors should
keep statements scoped to documented behavior, distinguish live beta features
from planned or historical features, preserve links to the canonical reference,
and avoid unverified market, audit, decentralization, or safety claims.

- Read [CONTRIBUTING.md](CONTRIBUTING.md) before proposing a change.
- Follow [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) when participating.
- Report suspected security issues privately using [SECURITY.md](SECURITY.md).

The documentation describes a technical beta. Verify current product status,
package versions, contract addresses, source matches, and transaction details
through official channels before relying on them or signing an irreversible
transaction.

## License

Documentation in this repository is released under the [MIT License](LICENSE).