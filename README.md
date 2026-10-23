
Color: the **DNS** state is cyan, **5xx** is magenta, everything else is plain. A `:80` that merely redirects to a live `:443` is dropped as a duplicate; a `:80` running a genuinely different app is kept. Summary at the end shows total / live / dns and elapsed time.

Use `-j` for JSON output with metadata (`hosts_total`, `hosts_live`, `hosts_dns`, timestamp, tool version) and a `hosts` array of records. Built to pipe straight into reKover.

---

## Testbed

Test disKover against a live target built specifically for this tool:

**https://sub.brutelogic.net**

12 unique subdomains across all techniques, live or DNS-only, and a dangling CNAME.

---

## 👑 King of Noobs

*We are all eternal noobs.*

This project was born from a simple truth: no matter how deep we go into security, we remain eternal noobs. There is always more to learn, and humility is our greatest advantage.

*"King of Noobs"* was originally thrown at me on X as an insult — because I kept sharing things in the simplest possible way, following KISS and the Pareto principle, instead of gatekeeping behind complexity.

I decided to wear the crown.

Not because I claim to be the best, but because the real elite are those who never stop being students. The ones who stay humble, build useful things, and help others level up without ego.

That's what King of Noobs is about.

### KISS

Originally "Keep It Simple, Stupid!" — used here as **Keep It Simple and Short**. Another K, intentional. The tools are short by design. Short means readable. Readable means auditable. Auditable means trustworthy.

### The K

The **K** in every tool name is the crown. Always uppercase. Always there.

| Tool | Purpose |
|------|---------|
| **reKon** | Master orchestrator — runs the full recon pipeline |
| **disKover** | Subdomain discovery |
| **reKover** | URL mapping (passive + brute + crawl) |
| **unKover** | 403 bypass / access control evasion |

---

*A [Brute Logic](https://brutelogic.net) project.*

---

## License

MIT
