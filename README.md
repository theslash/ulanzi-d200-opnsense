# Ulanzi D200 – OPNsense WAN Traffic Plugin

Shows live OPNsense up- and downstream (MB/s) on an [Ulanzi D200](https://www.ulanzi.com/) key.

## Features

- Live WAN download / upload rates in MB/s
- Polls the OPNsense API (self-signed TLS supported)
- Tap the key to open the OPNsense web UI
- Configurable host, API key/secret, interface, poll interval

## Requirements

- macOS or Windows with [Ulanzi Studio](https://www.ulanzi.com/pages/ulanzi-app)
- OPNsense with API access
- API user privileges for Diagnostics Traffic / Interface Statistics
- Node.js 20+ (only to build from source)

## Config

Copy the example and fill in your credentials:

```bash
cp com.ulanzi.opnsense.ulanziPlugin/local-config.example.json \
   com.ulanzi.opnsense.ulanziPlugin/local-config.json
```

Example (anonymized):

```json
{
  "host": "https://opnsense.home.arpa",
  "api_key": "example_opnsense_api_key_replace_me",
  "api_secret": "example_opnsense_api_secret_replace_me",
  "interface": "wan",
  "poll_seconds": "60",
  "insecure_tls": true
}
```

`local-config.json` is gitignored — do not commit real secrets.

API keys: **System → Access → Users → [User] → API keys**.

## Install (macOS)

```bash
./install.sh
```

Then restart **Ulanzi Studio**, drag **WAN Traffic** onto a key.

Manual install path:

`~/Library/Application Support/Ulanzi/UlanziDeck/Plugins/com.ulanzi.opnsense.ulanziPlugin`

## Build from source

```bash
cd com.ulanzi.opnsense.ulanziPlugin
npm install
npm run build
```

## License

MIT
