
# Linux & Windows Privilege Escalation Dataset

A structured dataset of known privilege escalation techniques for both **Linux** and **Windows** systems. Each entry includes a command, context, severity rating, mapped MITRE ATT&CK technique, and a reference link for further study.

This dataset is designed for use in:
- Red team operations
- LLM fine-tuning
- Privilege escalation simulations
- OSINT automation and enumeration tools
- Cybersecurity education and training

---

## 📁 Dataset Format

The dataset is saved in `.jsonl` (JSON Lines) format — each line represents one escalation vector.

### Fields:

| Field             | Description |
|------------------|-------------|
| `id`             | Unique identifier (e.g., `1`, `2`) |
| `platform`       | Operating system (`Linux` or `Windows`) |
| `command`        | Command used to detect or exploit privilege escalation |
| `description`    | Explains the purpose and function of the command |
| `category`       | Escalation type (e.g., SUID Binaries, Cron Jobs, Services) |
| `severity`       | Risk level: `Low`, `Medium`, `High`, or `Critical` |
| `mapped_technique` | MITRE ATT&CK ID (e.g., `T1548.001`) |
| `reference`      | URL to a trusted source or documentation |

---

## 🔍 Example Entry

```json
{
  "id": "1",
  "platform": "Linux",
  "command": "find / -perm -u=s -type f 2>/dev/null",
  "description": "Search for SUID binaries that might allow privilege escalation.",
  "category": "SUID Binaries",
  "severity": "High",
  "mapped_technique": "T1548.001",
  "reference": "https://gtfobins.github.io"
}
✅ Categories Covered
Linux:

    SUID Binaries

    Cron Jobs

    Kernel Exploits

    Writable Scripts

    Environment Misconfigurations

Windows:

    Unquoted Service Paths

    AlwaysInstallElevated

    Token Impersonation

    Registry Escalations

    DCOM & WMI Exploits

🧠 MITRE ATT&CK Mapping

Each entry is aligned with MITRE ATT&CK Tactics and Techniques (e.g. T1548, T1053, T1068) to support detection and adversary emulation workflows.
📊 Dataset Stats

    🎯 Platforms: Linux & Windows

    📌 Total entries: ~300 (expandable)

    🧪 Coverage: Manual commands, post-exploitation enumeration, exploitable misconfigurations

🛠 Use Cases

    Fine-tune LLMs for cybersecurity operations

    Build CLI tutors or CTF training engines

    Integrate into tools like linPEAS/winPEAS

    Red/Blue team playbooks and exercises

📜 License

Released under the MIT License. Use, share, modify freely — attribution appreciated.
🙌 Contributions

PRs welcome to expand, improve descriptions, or include platform-specific detection techniques.
