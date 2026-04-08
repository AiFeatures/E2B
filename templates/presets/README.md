# E2B Policy Presets (experimental)

Opinionated, enterprise-ready sandbox policy presets. Select a preset by name
instead of hand-editing source.

| Preset | Internet | Code exec | GPU | Intended use |
|---|---|---|---|---|
| `locked-down` | blocked | restricted | no | regulated / offline evaluation |
| `internet-enabled` | allowed | standard | no | research assistants, web tools |
| `gpu-enabled` | allowed | standard | yes | training, inference, vision |

Presets are JSON files in this directory. A preset is a documented *contract*,
not a runtime; the platform integration layer reads the file and applies the
corresponding sandbox flags.

## Selecting a preset

```bash
# future CLI (planned)
e2b template create --preset locked-down my-template

# today: reference the JSON file directly in your template config
cat templates/presets/locked-down.json
```

## Status

Minimum delighter slice (Wave 3 P1). Presets are documented and testable but
are not yet wired into the sandbox runtime. See `tests/presets.test.json` for
schema coverage.
