# 🍯 T-Pot Honeypot Lab

A live honeypot on the public internet, built to watch real attacks as they happen.

---

## Why I built this

I'm building a honeypot to monitor and see how attacks happen and how they start.
Catching something early is better than waiting until it's already happened.

## The bigger goal

I want to make this both a **SOC lab** and a **honeypot lab** in one, so I can watch the logs and the honeypot together.

---

## Tech used

| Part | What I used |
|---|---|
| Server | Contabo Cloud VPS (6 vCPU, 12 GB RAM, 200 GB SSD) |
| Operating system | Ubuntu 26.04 |
| Honeypot platform | T-Pot (Hive / standard install) |
| Access | SSH with key only |
| Troubleshooting | mtr |

---

## Choosing a host

1. **Oracle Cloud (free tier)**: my first choice because it was free, but it was constantly out of capacity
2. **Contabo (VPS)**: I switched to Contabo because they had affordable prices for what I needed

---

## Setup

1. Upgraded the server from **Ubuntu 24.04 to 26.04**, because T-Pot wouldn't install on the older version
2. Installed **T-Pot**, and I'm now actively watching attacks come in

---

## Hardening

1. Created a **separate admin user** instead of using root
2. **Blocked root login** over SSH
3. Turned off **password login** for SSH
4. I only log in with an **SSH key**, which is much safer
5. This means attackers **can't brute force** their way in

---

## Problem I found: packet loss

1. Large downloads from the server kept getting cut off partway, so dashboards like Kibana and the attack map wouldn't load
2. I used **mtr** to trace the route from my home in South Africa to the server
3. The route was clean all the way to Contabo's network edge
4. The loss (around **40%**) showed up **inside their network, near my server**
5. While waiting, I used an **SSH tunnel** to reach the dashboard, which got Elasticvue working
6. I reported it to Contabo support with the mtr results as evidence
7. Contabo **migrated my server to a new host**, keeping the same IP and data
8. After the move, everything loaded properly ✅

**What I took from it:** finding the problem, proving where it was with evidence, and reporting it clearly got it fixed.

---

## 📊 Findings

| Report | Dates | Highlights |
|---|---|---|
| [Week 1](reports/week-1.md) | Oct 14, 2026 – Oct 18, 2026 | 7.9 million events, top password `123456`, mdrfckr backdoor caught |

---

## 🦠 Malware

| Sample | Type | Verdict |
|---|---|---|
| [mdrfckr SSH backdoor](malware/mdrfckr-ssh-backdoor.md) | SSH keys + config | Known botnet (Outlaw / Dota), active since 2018 |

---

## 🚨 Incidents

| Incident | Date | Outcome |
|---|---|---|
| [Critical PHP CVEs](incidents/2026-10-php-cve-response.md) | Oct 21, 2026 | Host not exposed; vulnerable PHP found in a container and contained |

---

## 🛠️ Tools

**[Shark Log](tools/shark-log.html)**: my own tool for writing up findings and malware.

1. Download `tools/shark-log.html` and open it in a browser
2. Fill in the steps (or paste results straight from Elasticvue)
3. It makes the `.md` file for the `reports/` or `malware/` folder, plus the line to add to the tables above

My saved searches are in [queries](queries/README.md).

---

## Screenshots

_Coming soon_

<!-- Add screenshots to a /screenshots folder and link them here.
     Crop out your server IP and any login details first. -->
