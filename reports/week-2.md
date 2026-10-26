# 📊 Findings Report: Week 2

**Dates covered:** Oct 19, 2026 to Oct 25, 2026

**Written by:** HyperionFae

---

## ⭐ Headline

Over 10 million events in one week, led by more than 2.5 million hits on Windows Remote Desktop (port 3389).

---

## 1. 📈 The numbers

### Events per day

| Day | Events | Storage | Notes |
|---|---|---|---|
| Oct 19 | 1,209,902 | 566 MB |  |
| Oct 20 | 1,075,006 | 525 MB | Quietest day |
| Oct 21 | 1,959,918 | 804 MB | Busiest day, PHP2Shell disclosed |
| Oct 22 | 1,575,846 | 739 MB |  |
| Oct 23 | 1,238,131 | 629 MB |  |
| Oct 24 | 1,318,823 | 674 MB |  |
| Oct 25 | 1,815,067 | 865 MB |  |

| Stat | Value |
|---|---|
| Total events | 10,192,693 |
| Busiest day | Oct 21 (1,959,918 events) |

---

## 2. 🌍 Where from

### Top countries

| # | Country | Events |
|---|---|---|
| 1 | United States | 2,429,002 |
| 2 | France | 1,957,205 |
| 3 | The Netherlands | 1,411,244 |
| 4 | Germany | 1,391,181 |
| 5 | Kazakhstan | 1,063,923 |
| 6 | Bulgaria | 771,160 |
| 7 | China | 585,832 |
| 8 | Ukraine | 487,125 |
| 9 | United Kingdom | 269,931 |
| 10 | Singapore | 268,205 |

---

## 3. 🎯 What they targeted

### Busiest honeypots

| # | Honeypot | What it pretends to be | Events |
|---|---|---|---|
| 1 | P0f | Not a honeypot: guesses attackers' operating systems | 6,904,593 |
| 2 | Suricata | Not a honeypot: network intrusion detection | 4,299,860 |
| 3 | Fatt | Not a honeypot: fingerprints network traffic | 734,202 |
| 4 | RDPHoneypot | Windows Remote Desktop | 558,987 |
| 5 | Honeytrap | Any unused port | 365,644 |
| 6 | Sentrypeer | Internet phone (SIP) server | 321,746 |
| 7 | Cowrie | SSH and Telnet server | 309,093 |
| 8 | Dionaea | Windows file sharing, SQL, FTP and more | 142,150 |
| 9 | ConPot | Industrial control systems (ICS) | 45,938 |
| 10 | Honeyaml | Fake web API | 40,884 |

### Most-hit ports

| # | Port | Usually used for | Events |
|---|---|---|---|
| 1 | `3389` | Windows Remote Desktop (RDP) | 2,531,395 |
| 2 | `445` | Windows file sharing (SMB) | 973,453 |
| 3 | `5900` | VNC remote screen | 802,305 |
| 4 | `5060` | Internet phone calls (SIP) | 673,297 |
| 5 | `161` | Network device monitoring (SNMP) | 495,397 |
| 6 | `22` | SSH | 475,028 |
| 7 | `3000` | Web apps and dev servers | 390,603 |
| 8 | `443` | HTTPS websites | 372,147 |
| 9 | `53` | DNS | 156,855 |
| 10 | `80` | HTTP websites | 124,238 |

---

## 4. 🔑 How they tried to get in

### Top passwords

| # | Password | Tries |
|---|---|---|
| 1 | `(Blank)` | 139,518 |
| 2 | `123456` | 2,388 |
| 3 | `123` | 1,108 |
| 4 | `1234` | 995 |
| 5 | `345gs5662d34` | 876 |
| 6 | `3245gs5662d34` | 869 |
| 7 | `linuxshell` | 725 |
| 8 | `12345678` | 617 |
| 9 | `password` | 614 |
| 10 | `root` | 489 |
| 11 | `12345` | 460 |
| 12 | `1` | 451 |
| 13 | `admin` | 395 |
| 14 | `123456789` | 310 |
| 15 | `111111` | 213 |

### Top usernames

| # | Username | Tries |
|---|---|---|
| 1 | `administrator` | 50,226 |
| 2 | `Administrator` | 44,693 |
| 3 | `admin` | 29,299 |
| 4 | `root` | 20,473 |
| 5 | `(Blank)` | 14,096 |
| 6 | `sa` | 12,940 |
| 7 | `ubuntu` | 1,091 |
| 8 | `user` | 960 |
| 9 | `Administrateur` | 890 |
| 10 | `345gs5662d34` | 876 |
| 11 | `enable` | 725 |
| 12 | `server` | 631 |
| 13 | `postgres` | 534 |
| 14 | `deploy` | 521 |
| 15 | `test` | 473 |

---

## 5. 🚨 Known attacks (Suricata)

| # | Alert / CVE | Times | What it targets |
|---|---|---|---|
| 1 | SURICATA AF-PACKET truncated packet | 188,545 |  |
| 2 | SURICATA IPv4 truncated packet | 188,363 |  |
| 3 | SURICATA STREAM Packet with invalid timestamp | 64,945 |  |
| 4 | SURICATA STREAM Packet with broken ack | 30,164 |  |
| 5 | SURICATA STREAM spurious retransmission | 19,097 |  |
| 6 | ET INFO SSH session in progress on Expected Port | 9,454 |  |
| 7 | GPL ICMP Destination Unreachable Communication with Destination Host is Administratively Prohibited | 4,077 |  |
| 8 | SURICATA Applayer Detect protocol only one direction | 3,173 |  |
| 9 | SURICATA HTTP Response excessive header repetition | 2,923 |  |
| 10 | SURICATA STREAM reassembly sequence GAP -- missing packet(s) | 2,760 |  |

---

Most of these alerts are network noise (truncated or messy packets), not real attacks. Learning to tell noise from real threats was part of this week.

## 6. 🧠 My thoughts

### What surprised me

1. Attackers tried "Administrateur", the French name for the Windows admin account, showing bots target non-English systems too.

---

## 🔎 How I got this data

Searches from [queries](../queries/README.md), run in Elasticvue against the `logstash-*` indices.
