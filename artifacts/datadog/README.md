# artifacts/datadog

UBI-240 slice 6: the canonical home for this provider's own docs/codegen
artifacts, moved here from `ubiquex-docs`. See `ubx-sdk-kubernetes`'s
own `artifacts/kubernetes/README.md` for the full account of why this
moved (UBI-102's own comment thread) and how the four files divide.

- **`descriptions.json`** / **`intros.json`** / **`categories.json`** /
  **`exclusions.json`** — real source of truth, read by
  `ubx-docs-providers` at build time.
- **`datadog.json`** — codegen-ready export (`{resource: {relPath:
  text}}`, qualifier-stripped, HTML-unescaped). What `ubx sdk gen
  --descriptions-dir artifacts/datadog` actually reads. Never edited
  directly.

To update: edit `descriptions.json` here, then regenerate `datadog.json`
from a sibling `ubiquex-docs` checkout:

```bash
ubx sdk gen --only datadog --dump-ir /tmp/dump --out /tmp/unused
cd ~/Ubiquex/ubiquex-docs/scripts/resource-reference-gen
python3 export_raw_descriptions.py datadog Datadog \
    --dump-root /tmp/dump/datadog \
    --descriptions-path ~/Ubiquex/ubx-sdk-datadog/artifacts/datadog/descriptions.json \
    --nested-out ~/Ubiquex/ubx-sdk-datadog/artifacts/datadog/datadog.json
```

Commit both files together.
