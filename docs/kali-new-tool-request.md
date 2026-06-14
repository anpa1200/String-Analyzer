# Kali Linux New Tool Request: String Analyzer

Submit under **New Tool Requests** at <https://bugs.kali.org/>.

Do not submit this through `kali-meta`; Kali maintainers directed new tool
requests to the bug tracker workflow documented at:
<https://www.kali.org/docs/tools/submitting-tools/>.

## Summary

string-analyzer - categorized strings for malware and CTI triage

## Description

[Name] - String Analyzer

[Version] - 2.0.0

Use the tagged release, not a moving branch:
<https://github.com/anpa1200/String-Analyzer/releases/tag/v2.0.0>

[Homepage] - <https://github.com/anpa1200/String-Analyzer>

[Download] -

- Release: <https://github.com/anpa1200/String-Analyzer/releases/tag/v2.0.0>
- PyPI: <https://pypi.org/project/string-analyzer/>

[Author] - String Analyzer contributors / Andrey Pautov

[Licence] - GPL-3.0-or-later

[Description] - String Analyzer extracts printable ASCII and UTF-16LE strings
from binaries, memory artifacts, or disk images and categorizes security-relevant
findings for malware analysis, reverse engineering, forensics, and CTI triage.
It identifies URLs, IPs, emails, registry keys, Windows paths, DLL names, API
names, commands, suspicious keywords, Base64/hex candidates, and obfuscation
patterns. It can emit a categorized analyst report, unfiltered strings, or an
AI-ready markdown prompt for follow-up analysis.

[Dependencies] -

- Python >= 3.8
- No runtime third-party Python dependencies; standard library only

Development-only dependencies:

- pytest >= 7.0
- ruff >= 0.1.0

[Similar tools] - GNU strings/binutils, rabin2, floss, capa, bulk-extractor,
foremost. String Analyzer is focused on categorized security triage and
analyst-ready output rather than raw string extraction only.

[Activity] - Active. Public release v2.0.0 was published on 2026-06-14. The
project includes PyPI packaging, a tagged GitHub release, CI, tests, CLI and
library usage, and a practical usage guide.

[How to install] -

From the tagged PyPI release:

```bash
pipx install string-analyzer
string-analyzer --help
```

Or from the release source archive:

```bash
wget https://github.com/anpa1200/String-Analyzer/archive/refs/tags/v2.0.0.tar.gz
tar -xf v2.0.0.tar.gz
cd String-Analyzer-2.0.0
python3 -m venv .venv
. .venv/bin/activate
pip install .
string-analyzer --help
```

[How to use] -

```bash
string-analyzer /path/to/binary -o report.txt
string-analyzer /path/to/binary --unfiltered -o strings.txt
string-analyzer /path/to/binary --ai-prompt -o prompt.md
```

[Packaged] - Not currently packaged in Debian or Kali. The project is a pure
Python CLI with no runtime third-party dependencies, which should make packaging
straightforward.
