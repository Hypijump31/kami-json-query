# kami-json-query

[![KAMI Plugin](https://img.shields.io/badge/KAMI-plugin-8A2BE2)](https://github.com/Hypijump31/KAMI)
[![Signed](https://img.shields.io/badge/Ed25519-signed-green)](https://github.com/Hypijump31/kami-registry)

Transform JSON objects: pick keys, merge, sort, flatten, extract keys/values.

## Install

```bash
kami install Hypijump31/kami-json-query@v0.1.0
```

## Usage

```bash
# Pick specific keys
kami exec dev.kami.json-query '{"action": "pick", "data": {"a": 1, "b": 2, "c": 3}, "keys": ["a", "c"]}'

# Merge two objects
kami exec dev.kami.json-query '{"action": "merge", "data": {"a": 1}, "extra": {"b": 2}}'

# Get sorted keys
kami exec dev.kami.json-query '{"action": "sort_keys", "data": {"z": 1, "a": 2, "m": 3}}'

# Flatten nested object
kami exec dev.kami.json-query '{"action": "flatten", "data": {"a": {"b": {"c": 1}}}}'
```

## Arguments

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `action` | string | yes | `pick` | `merge` | `sort_keys` | `keys` | `values` | `flatten` |
| `data` | object | yes | JSON object to transform |
| `keys` | array | no | Key names to extract (required for `pick`) |
| `extra` | object | no | Additional object (required for `merge`) |

## Build from source

```bash
git clone https://github.com/Hypijump31/kami-json-query
cd kami-json-query
kami build . --release
```

To also package as plugin.zip:

```bash
kami build . --release --package
```

## Security

- Filesystem: none
- Network: none
- Max memory: 16 MB
- Max execution: 1000 ms

## License

MIT
