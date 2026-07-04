# `learn-web-hacking` — Repository Audit & Redesign Blueprint

*Prepared as a senior pentester / AppSec researcher / curriculum designer / OSS maintainer review.*
*Based on the live repository at `github.com/itachi-re/learn-web-hacking` (pulled directly via the GitHub API for this review).*

---

## 0. Current State — What's Actually There

Pulling the real tree instead of working from a guess:

```
learn-web-hacking/
├── LICENSE                    (MIT)
├── README.md                  (very solid outline — see below)
└── guides/
    ├── phase-0-foundation.md      (414 lines)
    ├── resources-guide.md         (507 lines)
    └── tools-setup-guide.md       (639 lines)
```

That's it. No `.github/`, no docs beyond three files, no CI, no templates.

**The good news:** `README.md` is already better than 90% of "awesome-hacking" list-repos. It has a real table of contents, a 5-phase structure (0–4), a 30-day quickstart, a progress checklist, a legal/ethics disclaimer, and a study-technique section (the "90-minute rule"). `guides/phase-0-foundation.md` is genuinely well-written — objectives, day-by-day breakdown, curl exercises, resource links. This isn't a repo that needs a rewrite from zero; it needs its skeleton filled in and its plumbing fixed.

**The critical problem:** the README's own internal links don't resolve.

| README links to | Actually exists? |
|---|---|
| `docs/phase-0-foundation.md` | ❌ (file is at `guides/phase-0-foundation.md` — wrong folder name) |
| `docs/phase-1-core-vulnerabilities.md` | ❌ does not exist |
| `docs/phase-2-tools-automation.md` | ❌ does not exist |
| `docs/phase-3-real-world.md` | ❌ does not exist |
| `docs/phase-4-specialization.md` | ❌ does not exist |
| `docs/tools.md`, `docs/certifications.md`, `docs/bug-bounty.md`, `docs/30-day-plan.md` | ❌ none exist |

So every visitor who clicks past Phase 0 hits a 404. For a repo whose entire value proposition is "a structured learning path," broken navigation is the single most damaging thing it can have — it's fixed first, before anything below.

---

## 1. Complete Repository Review

### Strengths to keep
- **Voice and structure of `README.md`** — keep the phase framing, the prerequisites section, the legal disclaimer, and the study-technique content. Don't rewrite these from scratch; relocate and extend them.
- **`phase-0-foundation.md`** is a genuine model for what every other guide should look like: objectives → day-by-day breakdown → resources → practical exercises.
- **`resources-guide.md` and `tools-setup-guide.md`** are meaty (500+ lines each) — likely just need de-duplication against the new `resources/` and `tools/` folders rather than a rewrite.
- MIT license is already in place — correct choice for a learning repo you want people to fork and adapt.

### Structural gaps
1. **No `.github/` at all** — no issue templates, no PR template, no workflows, no `CODEOWNERS`, no `FUNDING.yml`. Nothing enforces quality or contribution consistency.
2. **Single flat `guides/` folder** with no phase subfolders — doesn't scale past a handful of files, and doesn't match what the README already promises (5 phases).
3. **No `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `CHANGELOG.md`** — for a repo actively soliciting PRs ("Contributions are welcome!"), there's no actual process defined.
4. **No cheatsheets, no glossary, no writeups, no vulnerable-apps notes, no docker configs, no diagrams, no scripts** — these are the folders that turn a "reading list" into a genuine hands-on resource.
5. **No GitHub Topics set, no badges beyond License/PRs-welcome** (no CI badge, no last-updated badge, no discussions link).
6. **Discussions and Wiki are enabled at the API level** (`has_discussions` is technically available, `has_wiki: true`) but neither appears to be in active use — a missed, free engagement channel.
7. **No automated link-checking** — which is exactly how the `docs/` vs `guides/` mismatch above went unnoticed.

### Content/curriculum gaps
- Only **Phase 0** has an actual guide. Phases 1–4 exist only as headers in the README with no linked content — meaning ~90% of the promised curriculum doesn't exist yet.
- No coverage at all for: **GraphQL, WebSockets, JWT attacks, CSP, Prototype Pollution, NoSQL injection, Web Cache Deception, Request Smuggling, HTTP/2 & HTTP/3, Cloud Security** — all of which are explicitly named as scope for this redesign, and all of which are now standard in modern curricula (PortSwigger's Academy added Prototype Pollution, NoSQL injection, Web Cache Deception, and even a "Web LLM attacks" path as current topics).
- The recommended lab list mixes actively maintained projects with essentially archived ones without saying so (see §6 — Labs).
- The certification table lists things like BSCP, eJPT, PWPA/PNPT, OSCP/OSWE, eWPT/eWPTX, GWAPT with no guidance on *sequencing* relative to the phases.

### GitHub best-practice gaps
- No **markdown lint** or **spell-check** CI — for a text-only repo, this is the cheapest possible quality gate and it's absent.
- No **broken-link checker** — ironic, given the current state of the README.
- No **issue templates** — so "content request" / "broken link" / "typo" reports have no structure.
- No **CODEOWNERS**, no branch protection signaling, no release tagging (no Releases used at all despite the repo supporting them).

---

## 2. Improved Repository Structure

```text
learn-web-hacking/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.yml            # broken link, typo, factual error
│   │   ├── content_request.yml       # "please cover topic X"
│   │   └── new_resource.yml          # suggest a tool/course/writeup
│   ├── PULL_REQUEST_TEMPLATE.md
│   ├── workflows/
│   │   ├── markdown-lint.yml         # markdownlint-cli2
│   │   ├── link-check.yml            # lychee or markdown-link-check
│   │   ├── spellcheck.yml            # cspell with a custom infosec dictionary
│   │   └── toc-generator.yml         # auto-regenerate README ToC on merge
│   ├── CODEOWNERS
│   ├── FUNDING.yml
│   └── SECURITY.md
├── assets/
│   ├── banners/
│   ├── screenshots/
│   └── badges/
├── diagrams/
│   ├── http-request-lifecycle.mmd
│   ├── tls-handshake.mmd
│   ├── same-origin-policy-vs-cors.mmd
│   ├── oauth2-authorization-code-flow.mmd
│   ├── jwt-structure-and-attacks.mmd
│   ├── request-smuggling-cl-te.mmd
│   └── README.md                     # explains the Mermaid convention used repo-wide
├── guides/
│   ├── phase-0-foundations/
│   │   ├── 00-mindset-and-ethics.md
│   │   ├── 01-linux-fundamentals.md
│   │   ├── 02-networking-tcpip-dns.md
│   │   ├── 03-http-and-https.md
│   │   ├── 04-web-server-architecture.md
│   │   ├── 05-browser-internals-devtools.md
│   │   ├── 06-javascript-basics-for-hackers.md
│   │   ├── 07-python-basics-for-hackers.md
│   │   └── 08-git-and-github-workflow.md
│   ├── phase-1-recon-and-tooling/
│   │   ├── 01-recon-methodology.md
│   │   ├── 02-subdomain-enumeration.md
│   │   ├── 03-content-discovery-fuzzing.md
│   │   └── 04-burp-suite-mastery.md
│   ├── phase-2-application-mechanics/
│   │   ├── 01-authentication-mechanisms.md
│   │   ├── 02-sessions-and-cookies.md
│   │   ├── 03-jwt-attacks.md
│   │   ├── 04-cors.md
│   │   ├── 05-csp.md
│   │   ├── 06-oauth2-and-oidc.md
│   │   ├── 07-rest-api-security.md
│   │   ├── 08-graphql-security.md
│   │   └── 09-websockets.md
│   ├── phase-3-core-vulnerabilities/
│   │   ├── 01-sql-injection.md
│   │   ├── 02-cross-site-scripting.md
│   │   ├── 03-csrf.md
│   │   ├── 04-ssrf.md
│   │   ├── 05-xxe.md
│   │   ├── 06-ssti.md
│   │   ├── 07-command-injection.md
│   │   ├── 08-path-traversal.md
│   │   ├── 09-file-upload-vulnerabilities.md
│   │   └── 10-insecure-deserialization.md
│   ├── phase-4-advanced-exploitation/
│   │   ├── 01-access-control-and-idor.md
│   │   ├── 02-business-logic-flaws.md
│   │   ├── 03-race-conditions.md
│   │   ├── 04-clickjacking.md
│   │   ├── 05-cache-poisoning-and-deception.md
│   │   ├── 06-http-request-smuggling.md
│   │   └── 07-http2-http3-quirks.md
│   ├── phase-5-modern-attack-surfaces/
│   │   ├── 01-cloud-security-fundamentals.md
│   │   ├── 02-api-security-deep-dive.md
│   │   ├── 03-prototype-pollution.md
│   │   ├── 04-nosql-injection.md
│   │   └── 05-emerging-surfaces-llm-apps.md
│   └── phase-6-professional-practice/
│       ├── 01-bug-bounty-methodology.md
│       ├── 02-writing-a-great-report.md
│       ├── 03-cvss-scoring.md
│       ├── 04-responsible-disclosure-and-law.md
│       └── 05-career-paths-and-portfolio.md
├── labs/
│   ├── lab-index.md                  # master table: lab → topic → platform → difficulty
│   ├── local-setup/
│   │   ├── vm-lab-environment.md
│   │   └── burp-ca-cert-setup.md
│   └── platform-walkthroughs-policy.md  # rules for what write-ups are/aren't allowed
├── vulnerable-apps/
│   ├── README.md                     # comparison table + maintenance status (see §6)
│   ├── juice-shop-notes.md
│   ├── webgoat-notes.md
│   ├── dvwa-notes.md
│   ├── crapi-notes.md                # modern API-focused option
│   └── security-shepherd-notes.md
├── docker/
│   ├── README.md
│   ├── juice-shop/docker-compose.yml
│   ├── dvwa/docker-compose.yml
│   ├── webgoat/docker-compose.yml
│   ├── crapi/docker-compose.yml
│   └── full-lab-stack/docker-compose.yml   # everything on one bridge network
├── cheatsheets/
│   ├── sql-injection-cheatsheet.md
│   ├── xss-cheatsheet.md
│   ├── ssrf-cheatsheet.md
│   ├── xxe-cheatsheet.md
│   ├── ssti-cheatsheet.md
│   ├── jwt-attacks-cheatsheet.md
│   ├── file-upload-bypass-cheatsheet.md
│   ├── burp-suite-shortcuts.md
│   └── regex-and-payload-encoding.md
├── writeups/
│   ├── portswigger-labs/             # your own solved-lab writeups
│   ├── ctf/
│   └── bug-bounty/                   # disclosed reports only, with program permission
├── scripts/
│   ├── recon/
│   ├── automation/
│   └── README.md                     # usage + "read before running" safety note
├── tools/
│   └── tools-index.md                # curated, categorized, with install one-liners
├── resources/
│   ├── books.md
│   ├── youtube-and-video.md
│   ├── blogs-and-research.md
│   ├── podcasts.md
│   └── communities-and-forums.md
├── references/
│   ├── rfc-index.md                  # RFC 7230/7231/9110, 6749/6750, 7519, etc.
│   ├── owasp-mappings.md             # cross-map guides ↔ OWASP Top 10 / ASVS / Testing Guide
│   └── cve-case-studies.md
├── glossary/
│   └── GLOSSARY.md
├── ROADMAP.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── CHANGELOG.md
├── FAQ.md
├── LICENSE
└── README.md
```

---

## 3–9. Gap Checklist (Missing Folders / Guides / Docs / Labs / Tools / Platforms / Phases)

### 3. Missing folders
`.github/`, `assets/`, `diagrams/`, `labs/`, `notes/`, `cheatsheets/`, `writeups/`, `vulnerable-apps/`, `docker/`, `scripts/`, `tools/`, `resources/`, `references/`, `glossary/` — none currently exist. Only `guides/` exists, flat.

### 4. Missing guides
Everything except `phase-0-foundation.md`. Concretely absent: recon/subdomain enumeration/content discovery, Burp Suite mastery, auth/sessions/JWT/CORS/CSP/OAuth/GraphQL/WebSockets, every individual vulnerability class (SQLi, XSS, CSRF, SSRF, XXE, SSTI, command injection, path traversal, file upload, deserialization), IDOR/access control, business logic, race conditions, clickjacking, cache poisoning, request smuggling, HTTP/2 & HTTP/3, cloud security, and the professional-practice track (bug bounty methodology, reporting, CVSS, disclosure law).

### 5. Missing documentation
`ROADMAP.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `CHANGELOG.md`, `FAQ.md`, a dedicated `GLOSSARY.md`, and split-out `resources/` and `references/` docs (currently everything is crammed into one `resources-guide.md`).

### 6. Missing labs / lab guidance
No `lab-index.md` mapping topic → lab → platform → difficulty. No Docker Compose files for local labs. No guidance distinguishing **actively maintained** vs **legacy** vulnerable apps — this matters:

| App | Status (verified) | Recommendation |
|---|---|---|
| **OWASP Juice Shop** | Actively maintained, modern JS/TS stack | Primary recommendation |
| **OWASP WebGoat** | Actively maintained by OWASP | Primary recommendation |
| **DVWA** | Maintained, updated periodically | Keep — good for absolute beginners |
| **OWASP Mutillidae II** | Still maintained (webpwnized fork), PHP/MySQL | Keep as secondary/legacy-stack practice |
| **bWAPP / bee-box** | Core project effectively frozen since ~2014; site still exists but content hasn't moved with the modern stack | Mark as *legacy* — useful for classic vuln patterns, not representative of modern apps |
| **XVWA** | Minimal ongoing activity | Mark as *optional/legacy* |
| **crAPI (OWASP)** | Actively maintained, API-specific | **Add** — nothing in the current README covers API-focused practice |
| **Security Shepherd** | OWASP-maintained | Consider adding for a guided-lesson alternative to WebGoat |

### 7. Missing tools
No categorized tools list beyond a short bash snippet in the README. Missing: recon tooling (subfinder, amass, httpx), content discovery (ffuf, feroxbuster, gobuster), proxy/interception beyond Burp/ZAP (mitmproxy), JWT tooling (jwt_tool), SSRF/XXE testing helpers, GraphQL-specific tools (InQL, GraphQL Voyager), request-smuggling tooling (Smuggler, HTTP Request Smuggler Burp extension), and API-specific tools (Postman/Insomnia + schema-based fuzzers).

### 8. Missing practice platforms
The README lists DVWA/bWAPP/Juice Shop/WebGoat/HackThisSite for local practice and CTFtime/PicoCTF/Root-Me/pwn.college for CTF — solid, but missing: **PortSwigger Web Security Academy's labs are only linked, never indexed** (no lab-by-lab tracker), **OverTheWire** (Natas is the actual web-focused wargame — not currently mentioned at all), **HackTheBox Academy's dedicated web modules**, **TryHackMe's web fundamentals path**, and **PentesterLab** (paid, but one of the highest-quality web-specific platforms available and conspicuously absent).

### 9. Missing learning phases
The README *names* 5 phases (0–4) but only Phase 0 has content, and it stops at "core vulnerabilities + tools + real-world + specialization" — it has no room for GraphQL, WebSockets, JWT, CSP, request smuggling, cache poisoning/deception, HTTP/2 & HTTP/3, cloud security, prototype pollution, or NoSQL injection, all of which are named as required scope here and all of which are current, examinable topics on PortSwigger's own Academy today. The redesign above expands 5 phases to 7 (0–6) specifically to give these topics a real home instead of squeezing them into "Phase 4: Specialization."

---

## 10. The Full Learning Roadmap

| Phase | Focus | Core Topics | Est. Duration |
|---|---|---|---|
| **0 — Foundations** | How the web actually works | Mindset/ethics, Linux, TCP/IP & DNS, HTTP/HTTPS, web server architecture, browser internals & DevTools, JS basics, Python basics, Git | 3–4 weeks |
| **1 — Recon & Tooling** | Finding and mapping attack surface | Recon methodology, subdomain enumeration, content discovery/fuzzing, Burp Suite mastery | 2 weeks |
| **2 — Application Mechanics** | The systems vulnerabilities live inside | Authentication, sessions & cookies, JWT, CORS, CSP, OAuth2/OIDC, REST APIs, GraphQL, WebSockets | 3–4 weeks |
| **3 — Core Vulnerabilities** | OWASP Top 10 and classic classes | SQLi, XSS, CSRF, SSRF, XXE, SSTI, command injection, path traversal, file upload, insecure deserialization | 8–10 weeks |
| **4 — Advanced Exploitation** | Beyond the basics | Access control/IDOR, business logic, race conditions, clickjacking, cache poisoning/deception, request smuggling, HTTP/2 & HTTP/3 quirks | 4–6 weeks |
| **5 — Modern Attack Surfaces** | What real targets look like today | Cloud security fundamentals, API security deep-dive, prototype pollution, NoSQL injection, LLM/AI-app attack surface | 4–6 weeks |
| **6 — Professional Practice** | Turning skill into a career/portfolio | Bug bounty methodology, report writing, CVSS scoring, responsible disclosure & law, career paths | Ongoing |

This is the same "phase" mental model the current README already uses — it's just given the room the full topic list actually needs, instead of trying to fit 25+ modern topics into "Phase 1" and "Phase 4."

---

## 11. Documentation Set (What Each File Should Do)

| File | Purpose |
|---|---|
| `README.md` | Landing page — pitch, ToC, quickstart, badges, links out to `ROADMAP.md` |
| `ROADMAP.md` | The full phase table above, with checkboxes per guide file |
| `CONTRIBUTING.md` | How to submit a guide, the required section template, style rules, DCO/sign-off if desired |
| `CODE_OF_CONDUCT.md` | Standard Contributor Covenant — matters once Discussions/Issues get real traffic |
| `SECURITY.md` | How to report a problem *with the repo* (e.g., a payload that could harm a reader's own machine) — distinct from bug bounty content |
| `CHANGELOG.md` | Keep-a-Changelog format, tied to Releases |
| `FAQ.md` | "Do I need to know programming first?", "Is this enough for OSCP?", "Can I use this for teaching?" |
| `glossary/GLOSSARY.md` | Every term used across guides, one definition each, alphabetized |
| `resources/*.md` | Split books/video/blogs/podcasts/communities instead of one long file |
| `references/*.md` | RFCs, OWASP ASVS/Testing Guide cross-mapping, notable CVEs as case studies |

---

## 12. GitHub Configuration & Automation

- **Topics**: `web-security`, `penetration-testing`, `owasp`, `bug-bounty`, `appsec`, `ctf`, `security-learning`, `burp-suite`, `ethical-hacking`
- **Badges**: License (have it), PRs Welcome (have it), + CI status (`markdown-lint`, `link-check`), a "guides completed" progress badge, GitHub stars
- **Issue templates**: bug/typo report, content request, new-resource suggestion (all as `.yml` forms, not free-text — cleaner triage)
- **PR template**: checklist enforcing the guide-template sections (§13) before merge
- **GitHub Actions**: `markdownlint-cli2` for style, `lychee` or `markdown-link-check` for dead links (this alone would have caught the `docs/` vs `guides/` mismatch), `cspell` with a custom infosec dictionary so tool/CVE names don't false-positive
- **Discussions**: enable and seed with categories — *Q&A*, *Show and tell (writeups)*, *Resource suggestions*
- **Wiki**: skip it in favor of the repo itself being the single source of truth (Wikis fragment search and drift out of sync with the main tree) — keep `has_wiki` off in practice even if enabled at the API level
- **Releases**: tag milestones ("v1.0 — Phase 0–2 complete") so returning learners can see what changed since their last visit
- **CODEOWNERS**: even solo, this signals maintained-review-required on guide folders

Given the automation pipelines already built for OBS packaging (nvchecker + GitHub Actions), the link-checker/lint workflows here are a much simpler version of the same pattern — same CI muscle, lower-stakes payload.

---

## 13. Guide Template (the "Learning Style" every guide file follows)

This is the skeleton — not filled-in course content, just the reusable structure every `guides/phase-*/NN-topic.md` file should share:

```markdown
# <Topic Name>

## 🎯 Learning Objectives
- [ ] Objective 1
- [ ] Objective 2

## 📖 Theory
<Concept explanation — what it is, why it exists, the underlying mechanism>

## 🖼 Diagram
<Link to /diagrams/topic.mmd, or inline Mermaid block>

## 🧪 Examples
<Minimal, illustrative request/response or code snippets>

## 🧩 Hands-On Labs
| Lab | Platform | Difficulty |
|---|---|---|
| ... | PortSwigger / Juice Shop / HTB / etc. | Easy–Hard |

## ✍️ Exercises
1. Exercise 1
2. Exercise 2

## ⚠️ Common Mistakes
- Mistake learners typically make and why

## ✅ Best Practices (Defender's View)
- How this vulnerability class is actually prevented

## 📚 Further Reading
- Official docs, RFCs, research

## 🗂 Checklist
- [ ] Can explain the vulnerability to someone else
- [ ] Can identify it in a request/response
- [ ] Can exploit it manually (no tools)
- [ ] Can automate detection

## ❓ Quiz
1–3 short recall questions (answers in a collapsible `<details>` block)

## 🏆 Challenge
One stretch task that goes beyond the labs above

## 🔗 References
- Numbered source list
```

Every existing guide (`phase-0-foundation.md`, etc.) should be retrofitted to this exact shape so the repo feels like one authored resource rather than a pile of notes.

---

## 14. Curated Resource Library (high-signal only)

| Category | Resource | Why it's here |
|---|---|---|
| **Structured learning** | [PortSwigger Web Security Academy](https://portswigger.net/web-security) | The gold standard — free, constantly updated, includes current topics like GraphQL, prototype pollution, NoSQL injection, web cache deception |
| | [OWASP Web Security Testing Guide (WSTG)](https://owasp.org/www-project-web-security-testing-guide/) | Canonical testing methodology reference |
| | [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard/) | Requirements-based checklist — great for the "best practices" section of every guide |
| | [Hack The Box Academy](https://academy.hackthebox.com/) | Structured modules, free + paid tiers |
| | [TryHackMe](https://tryhackme.com/) | Guided rooms, strong for absolute beginners |
| **Reference/standards** | RFC 7230/7231 (HTTP/1.1), RFC 9110 (HTTP Semantics), RFC 6749/6750 (OAuth2), RFC 7519 (JWT) | Primary sources — cite these, not blog paraphrases |
| | [MDN Web Docs](https://developer.mozilla.org/) | Best browser/JS/HTTP reference available |
| | [NIST SP 800-63 (Digital Identity Guidelines)](https://pages.nist.gov/800-63-3/) | Authoritative source for the authentication guide |
| **Bug bounty** | [HackerOne Hacktivity](https://hackerone.com/hacktivity) + [Bugcrowd University](https://www.bugcrowd.com/hackers/bugcrowd-university/) | Real disclosed reports + free structured training |
| | [MITRE CVE](https://cve.mitre.org/) / [CVE.org](https://www.cve.org/) | Case-study source material for `references/cve-case-studies.md` |
| **Books** | *The Web Application Hacker's Handbook* (Stuttard & Pinto) | Still the deepest manual-testing reference despite its age |
| | *Real-World Bug Hunting* (Yaworski) | Best "here's how real bugs were actually found" text |

Avoid: outdated "top 10 hacking sites" listicles, unmaintained forum wikis, and any source that hasn't been updated since before HTTP/2 was mainstream — the repo's credibility rests on every linked resource still being live and current.

---

## 15. Improvements Ranked by Priority

**P0 — Fix now (breaks trust in the repo as-is)**
1. Fix the `docs/` → `guides/` path mismatch throughout `README.md` (every Phase 0–4 link is currently dead)
2. Add a link-checker GitHub Action so this class of bug can't recur silently

**P1 — Foundational scaffolding (unlocks everything else)**
3. Create the full folder structure from §2, even as mostly-empty placeholder files with just an H1 and "🚧 in progress"
4. Write `CONTRIBUTING.md` + the guide template (§13) — every subsequent guide should be written *to* this template, not retrofitted later
5. Add `.github/ISSUE_TEMPLATE/`, PR template, `CODE_OF_CONDUCT.md`, `SECURITY.md`

**P2 — Core content (the actual value)**
6. Fill Phase 0 subfolder by splitting the existing 414-line `phase-0-foundation.md` into the 9 topic files
7. Write Phase 3 (Core Vulnerabilities) first, before Phases 1/2/4/5 — this is what most visitors are searching for and what most competing repos already do well, so it needs to be *better*, not just present
8. Build `vulnerable-apps/README.md` with the maintenance-status table from §6 — cheap to write, high trust value
9. Stand up 2–3 `docker/*/docker-compose.yml` files (Juice Shop, DVWA, WebGoat) so "hands-on" is one command away

**P3 — Polish and differentiation**
10. `glossary/GLOSSARY.md`, `cheatsheets/*`, `diagrams/*` (Mermaid, matching the convention already used in `butex-notes`)
11. GitHub Topics, badges, Discussions seeding, first tagged Release
12. Phases 1, 2, 4, 5, 6 content, roughly in that order

---

## 16. Additional Ideas to Stand Out

- **Lab tracker as data, not prose** — a `labs/lab-index.md` table (topic, platform, difficulty, link, ✅/⬜ status) is far more useful than the current inline bullet lists, and can later back a small GitHub Pages progress-tracker page.
- **OWASP/ASVS cross-mapping file** (`references/owasp-mappings.md`) — nothing in the current repo maps its own content back to OWASP Top 10 / ASVS control IDs, which is exactly what makes a resource feel "professional" versus "hobbyist."
- **A dedicated API security & modern-surfaces module** (crAPI, GraphQL, prototype pollution) — this is the single biggest gap versus where the industry actually is right now, and almost no beginner-focused repo covers it well, so it's a real differentiator.
- **Mermaid diagrams as a repo-wide convention** — this is already how `butex-notes` handles diagrams; reusing that same convention here keeps a consistent authoring style across projects and makes diagrams git-diffable instead of binary images.
- **Anki-exportable flashcards** generated from each guide's Quiz section — cheap to add, high retention value, easy to automate later.
- **A "0 to first PortSwigger lab solved" onboarding path** as a single pinned Discussion — lowers the activation energy for first-time visitors more than any amount of README polish.
- **Versioned Releases tied to phase completion** ("v0.1 — Phase 0 complete") — gives returning readers a changelog-driven reason to come back, and gives the repo a visible development narrative in its own right.
