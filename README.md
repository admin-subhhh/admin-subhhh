<div align="center"><img src="https://raw.githubusercontent.com/admin-subhhh/soc-journey/main/.github/social-preview.png" alt="Subrata Bera — SOC Journey" width="100%" />
Subrata Bera
SOC Analyst L1 track · blue team foundations → detection engineering → red team
Kolkata, India · building in public, one evidence-backed lab per day · open to entry-level SOC / security analyst roles

SOC Journey
Detections

</div>
What I am
A fresher who is building a SOC analyst skillset in public, with a rule that most learning portfolios do not have:

Every number in my repos is traceable to an artifact in my repos.

So every lab declares whether its data is live, synthetic, or platform-supplied, every hash is reproducible with one command, and every write-up has a "what I got wrong" section. I would rather show you a corrected mistake than a suspiciously clean record — because in a SOC the report is the work product, and a report nobody can audit is not worth writing.

I also broke that rule early on, documented it publicly, and rebuilt. That audit is here: docs/migration.md — it is the most honest thing in my profile and the thing I would most want you to read.

What I can actually do
SIEM / log analysis	Splunk SPL — stats, dc(), eval, count(eval()), where, correlation via bin+stats
Detection engineering	Sigma rules + correlations, CI-validated and compiled to SPL on every push
Windows / AD telemetry	4624 / 4625 / 4648 / 4672, logon types 2·3·10, SubStatus 0xC000006A vs 0xC0000064
Network	Wireshark, DNS/TCP/TLS analysis, nmap, pcap triage
Email / phishing	Return-Path vs From, homoglyph domains, bottom-up Received, SPF/DKIM/DMARC
Threat intel	VirusTotal, urlscan.io — including refusing to read 0/92 as "clean"
Frameworks	MITRE ATT&CK at sub-technique level (T1110.001/.003, T1566.001/.002), M1017/M1021
Tooling	Kali Linux, Splunk Enterprise, Sigma/sigma-cli, Git + GitHub Actions
Full evidence, day by day: github.com/admin-subhhh/soc-journey

Selected work
<table> <tr> <td width="50%" valign="top">
🔎 Phishing triage — the unknown-URL trap
Day 05 →

VirusTotal returned 0/92. The naive read is "clean". The correct read is unknown — status -, last analysed three months ago, on a freshly registered brand-lookalike domain with a /login path. Cross-checked against a live urlscan.io inspection and a known-clean control scan.

The judgement call, not the tool output, is the deliverable.

</td> <td width="50%" valign="top">
🛡️ Detection as code
detections/ →

Sigma base rule + correlation rule (≥5 failed logons per IP in 10 min), validated and compiled to Splunk SPL by GitHub Actions. Badge goes red if a rule breaks.

Found two real gotchas along the way: the | count() by pipe syntax is removed from modern pySigma, and tactic tags need a hyphen (attack.credential-access, not attack.credential_access).

</td> </tr> <tr> <td width="50%" valign="top">
📧 Email header forensics
Day 04 →

Four independent evidence layers on one message: envelope/header mismatch, 0-for-o Reply-To squat, bottom-up Received chain, and triple authentication failure with p=reject. Includes the forwarding false-positive I checked and rejected.

</td> <td width="50%" valign="top">
🧾 The audit I published on myself
migration.md →

My first five days had a fabricated IP ranking, a hash that was the SHA-256 of an empty file, and an inflated detection ratio. All three are documented, corrected, and turned into a 10-rule provenance policy I now work to.

This is what I mean by evidence-first.

</td> </tr> </table>
Currently
YAML

working_on:   Splunk correlation → Sigma correlation syntax; closing the write-up gap
learning:     detection efficacy testing (does the rule actually fire on the attack?)
reading:      ATT&CK credential-access + initial-access deep dives
next_up:      first LetsDefend / BTJA case with platform ground truth
target:       SOC Analyst L1 by Q2 2026
Contact
Hiring / roles	Open to entry-level SOC analyst, security analyst, and detection content roles — India or remote
Corrections	Genuinely welcome. Open an issue and point me at the artifact that proves me wrong — that is the fastest way to my respect
Location	Kolkata, West Bengal, India (IST, UTC+5:30)
<div align="center">
Not certified yet — working toward Security+. No production SOC experience yet. What I have is 5 days of documented, audited, reproducible lab work and a pipeline that proves it compiles. Judge the work, not the claims.

</div>
