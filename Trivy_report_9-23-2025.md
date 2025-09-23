skriptk1d@MacBookPro shai-hulud-detect % trivy fs --include-dev-deps --scanners vuln,secret,misconfig .
2025-09-23T10:53:09-04:00	INFO	[vuln] Vulnerability scanning is enabled
2025-09-23T10:53:09-04:00	INFO	[misconfig] Misconfiguration scanning is enabled
2025-09-23T10:53:10-04:00	INFO	[secret] Secret scanning is enabled
2025-09-23T10:53:10-04:00	INFO	[secret] If your scanning is slow, please try '--scanners vuln,misconfig' to disable secret scanning
2025-09-23T10:53:10-04:00	INFO	[secret] Please see https://trivy.dev/v0.66/docs/scanner/secret#recommendation for faster secret detection
2025-09-23T10:53:10-04:00	INFO	[npm] To collect the license information of packages, "npm install" needs to be performed beforehand	dir="test-cases/infected-lockfile/node_modules"
2025-09-23T10:53:10-04:00	INFO	[pnpm] To collect the license information of packages, "pnpm install" needs to be performed beforehand	dir="test-cases/infected-lockfile-pnpm/node_modules"
2025-09-23T10:53:10-04:00	INFO	Number of language-specific files	num=2
2025-09-23T10:53:10-04:00	INFO	[npm] Detecting vulnerabilities...
2025-09-23T10:53:10-04:00	INFO	[pnpm] Detecting vulnerabilities...
2025-09-23T10:53:10-04:00	INFO	Detected config files	num=0

Report Summary

┌──────────────────────────────────────────────────┬──────┬─────────────────┬─────────┬───────────────────┐
│                      Target                      │ Type │ Vulnerabilities │ Secrets │ Misconfigurations │
├──────────────────────────────────────────────────┼──────┼─────────────────┼─────────┼───────────────────┤
│ test-cases/infected-lockfile-pnpm/pnpm-lock.yaml │ pnpm │        0        │    -    │         -         │
├──────────────────────────────────────────────────┼──────┼─────────────────┼─────────┼───────────────────┤
│ test-cases/infected-lockfile/package-lock.json   │ npm  │        0        │    -    │         -         │
└──────────────────────────────────────────────────┴──────┴─────────────────┴─────────┴───────────────────┘
Legend:
- '-': Not scanned
- '0': Clean (no security findings detected)
