# flair-helm

flair-helm is FLAIR's official Helm chart collection — packaging every FLAIR component (agents as DaemonSets, `flair-core`, `flair-ui`, scoring rules) for one-command Kubernetes deployment. It owns deployment/infrastructure only, no application logic. See the [FLAIR org overview](https://github.com/flair-security/.github) for how it fits with the rest of the ecosystem.

**Status:** pre-MVP scaffolding — no charts committed yet. Listed as "planned" in the org roadmap, sequenced after the core MVP (`flair-agent` + `flair-core` + `flair-ui`) is solid.

## Stack

- Helm 3.17+
- Helmfile 0.168+
- Kubernetes >= 1.29

## Getting started

```bash
# Lint all charts
helm lint charts/*

# Template render (dry-run)
helm template flair charts/flair-core -f environments/dev/values.yaml

# Diff against a cluster (requires kubeconfig)
helm diff upgrade flair-core charts/flair-core -f environments/staging/values.yaml

# Helmfile diff (all releases)
helmfile diff -e staging

# Validate templates
helm template flair charts/flair-core | kubectl apply --dry-run=client -f -

# Schema validation
helm lint charts/flair-core --strict
```

## Documentation

Docs live in [flair-docs](https://github.com/flair-security/flair-docs) — the docs site itself is still under construction.

## Contributing

See the org-wide [CONTRIBUTING.md](https://github.com/flair-security/.github/blob/main/CONTRIBUTING.md).

## Security

See the org-wide [SECURITY.md](https://github.com/flair-security/.github/blob/main/SECURITY.md) for how to report vulnerabilities.

## License

Apache License 2.0 — see [LICENSE](LICENSE).
