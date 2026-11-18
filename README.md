<p align="center">
  <img src="logo/dark.svg#gh-dark-mode-only" alt="Custoden" height="40">
  <img src="logo/light.svg#gh-light-mode-only" alt="Custoden" height="40">
</p>

# Custoden API documentation

Source for the documentation of the [Custoden API](https://docs.custoden.com): a free, keyless API for checking npm and PyPI packages and GitHub Actions workflows for supply chain attacks.

```bash
curl https://api.custoden.com/v1/packages/npm/expres
```

## What the API covers

| Endpoint | Purpose |
|---|---|
| `GET /v1/packages/{ecosystem}/{name}` | Malware, install-time code, typosquatting and known vulnerabilities for one package |
| `POST /v1/packages/check` | Up to 10 packages in one request |
| `POST /v1/github/workflows/analyze` | Secret theft, script injection, risky actions and permission issues in a workflow |
| `GET /v1/github/repos/{owner}/{repo}/runs` | Workflows that actually ran, including ones later reverted or force-pushed away |
| `GET /v1/github/repos/{owner}/{repo}/scan` | Dependencies, workflows and CI files of a public repository in one request |

The full specification is in [`openapi.yaml`](openapi.yaml).

## Structure

| Path | Contents |
|---|---|
| `docs.json` | Site configuration and navigation |
| `introduction.mdx` | Home page |
| `getting-started/` | Quickstart, rate limits and errors |
| `api-reference/` | One page per endpoint |
| `reference/` | Finding IDs, workflow rules and tracked campaigns |
| `guides/` | CI integration examples |

## Preview locally

The site is built with [Mintlify](https://mintlify.com). Changes pushed to `main` are published automatically.

```bash
npm i -g mint
mint dev
```

Then open [http://localhost:3000](http://localhost:3000).

## Contributing

Corrections and new examples are welcome. Open an issue or a pull request. Run `mint broken-links` before submitting.

To report a security issue in the API itself, see [SECURITY.md](SECURITY.md) instead of opening a public issue.

## License

Documentation is licensed under [CC BY 4.0](LICENSE). Code samples, including the scripts and workflows in the guides, are licensed under the [MIT License](LICENSE-CODE) so you can copy them into your projects.
