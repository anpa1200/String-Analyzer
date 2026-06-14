# Kali New Tool Request Draft: string-analyzer

## Package

- **Tool name:** string-analyzer
- **Upstream:** https://github.com/anpa1200/String-Analyzer
- **PyPI:** https://pypi.org/project/string-analyzer/
- **License:** GPL-3.0-or-later
- **Language:** Python 3.8+
- **Runtime dependencies:** none outside the Python standard library
- **CLI:** `string-analyzer`

## Summary

String Analyzer extracts printable ASCII and UTF-16 strings from binary files,
memory artifacts, and disk images, then classifies the output into analyst-useful
categories: URLs, IP addresses, registry keys, system paths, DLLs, Windows APIs,
CMD/PowerShell commands, decoded Base64/hex candidates, suspicious keywords, and
obfuscation indicators.

## Why Kali

Kali already ships many low-level triage utilities. String Analyzer adds a
defender-friendly layer for malware analysts, reverse engineers, incident
responders, and CTI analysts who need categorized strings and AI-ready prompts
without building a custom pipeline around raw `strings` output.

## Use Cases

- Malware triage before full reverse engineering
- Incident-response artifact review
- Fast IOC discovery from suspicious binaries and memory dumps
- Prompt generation for analyst-assisted malware behavior summaries
- Batch processing through the Python API

## Install And Smoke Test

```bash
pip install string-analyzer
string-analyzer --help
string-analyzer suspicious.exe --filtered -o report.txt
string-analyzer suspicious.exe --ai-prompt -o prompt.md
```

## Safety

The tool performs local file parsing and reporting only. It does not exploit
targets, execute analyzed samples, or contact external APIs. AI integration is
optional and only invokes locally configured CLIs when the analyst explicitly
uses `--analyze-with`.

## Related Documentation

- README: https://github.com/anpa1200/String-Analyzer
- Detailed docs: https://github.com/anpa1200/String-Analyzer/blob/main/docs/DOCUMENTATION.md
- Medium guide: https://medium.com/@1200km/a-practical-guide-to-string-analyzer-extract-and-analyze-strings-from-binaries-without-the-875dc74e4868
