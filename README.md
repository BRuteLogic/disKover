# disKover

> *Discover what's below.*

Subdomain discovery by [Brute Logic](https://brutelogic.net).

Part of the **King of Noobs** suite, offensive recon tools built on KISS and the Pareto principle. Simple, fast, and effective.

---

## What It Does

disKover enumerates subdomains active-first, combining several techniques into one fast pipeline and confirming every result by live resolution:

1. **Brute** probes a high-probability prefix wordlist against the target zone
2. **SRV sweep** pulls service hosts from common SRV records (SIP, XMPP, LDAP, Kerberos, autodiscover, mail and more)
3. **NSEC zone walk** follows the DNSSEC NSEC chain to enumerate names in signed zones (NSEC3/hashed zones simply stop the walk)
4. **AXFR** attempts a zone transfer against each authoritative nameserver, which a misconfigured server answers with the full zone
5. **Apex mining** extracts sub references from the main site's HTML, CSP and Alt-Svc headers, robots.txt, sitemap.xml and referenced JavaScript (depth 1, same-scope only)
6. **Permutation** combines discovered labels with affix words to surface siblings
7. **Passive bonus** adds certificate transparency (crt.sh) when available, never a hard dependency

Every candidate passes a resolve gate with wildcard-DNS filtering, then live web probing across common ports, so output is confirmed hosts only. Results stream live, color-coded, with a DNS-only line for names that resolve but serve no web.

---

## Why Bash?

No runtime. No pip install. No npm. No supply chain risk.

Bash, curl and dig are already on every Linux box. The script is short, readable, and auditable by anyone in seconds. That is not a limitation, that is the point.

---

## Dependencies

```bash
sudo apt install parallel dnsutils -y
```

---

## Usage

```bash
bash diskover <DOMAIN> [-j|--json]
```

### Examples

```bash
bash diskover example.com
bash diskover example.com -j | jq
```

---

## Output

Live results color-coded as hosts are confirmed. Summary at the end with total resolved hosts, live web hosts, DNS-only hosts, and elapsed time.

Use `-j` for JSON output with metadata including tool version, timestamp, and per-host status, IP, port and CNAME.

---

## Testbed

Test disKover against a live target built specifically for this tool:

**https://sub.brutelogic.net**

12 unique subdomains across all techniques, live or DNS-only, including a dangling CNAME.

---

## 👑 King of Noobs

*We are all eternal noobs.*

This project was born from a simple truth: no matter how deep we go into security, we remain eternal noobs. There is always more to learn, and humility is our greatest advantage.

*"King of Noobs"* was originally thrown at me on X as an insult, because I kept sharing things in the simplest possible way, following KISS and the Pareto principle, instead of gatekeeping behind complexity.

I decided to wear the crown.

Not because I claim to be the best, but because the real elite are those who never stop being students. The ones who stay humble, build useful things, and help others level up without ego.

That's what King of Noobs is about.

### KISS

Originally "Keep It Simple, Stupid!", used here as **Keep It Simple and Short**. Another K, intentional. The tools are short by design. Short means readable. Readable means auditable. Auditable means trustworthy.

### The K

The **K** in every tool name is the crown. Always uppercase. Always there.

| Tool | Purpose |
|------|---------|
| **reKon** | Master orchestrator, runs the full recon pipeline |
| **disKover** | Subdomain discovery |
| **reKover** | URL mapping (passive + brute + crawl) |
| **unKover** | 403 bypass / access control evasion |

---

*A [Brute Logic](https://brutelogic.net) project.*

---

## License

MIT
