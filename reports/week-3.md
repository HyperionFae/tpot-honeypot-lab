# 📊 Findings Report: Week 3

**Dates covered:** Oct 26, 2026 to Nov 1, 2026

**Written by:** HyperionFae

---

## ⭐ Headline

Bots kept trying Windows admin names in other languages, with German "Systemverwalter" and "Verwalter" joining last week's French "Administrateur", and the Netherlands became the top attacking country.

---

## 1. 📈 The numbers

### Events per day

| Day | Events | Storage | Notes |
|---|---|---|---|
| Oct 26 | 3,776,280 | 1.3 GB | Full port scan from one IP |
| Oct 27 | 3,388,227 | 1.3 GB |  |
| Oct 28 | 3,494,904 | 1.3 GB |  |
| Oct 29 | 3,802,635 | 1.4 GB | Busiest day |
| Oct 30 | 2,163,782 | 964.9 MB | Quietest day |
| Oct 31 | 2,601,493 | 1.1 GB |  |
| Nov 1 | 2,491,992 | 1 GB |  |

| Stat | Value |
|---|---|
| Total events | 21,719,313 |
| Busiest day | Oct 29 (3,802,635 events) |
| Compared to Week 2 | More than double (10,192,693 → 21,719,313) |

---

## 2. 🌍 Where from

### Top countries

| # | Country | Events |
|---|---|---|
| 1 | The Netherlands | 3,796,197 |
| 2 | United States | 3,469,381 |
| 3 | France | 2,659,208 |
| 4 | Ukraine | 2,029,638 |
| 5 | Germany | 1,677,838 |
| 6 | Kazakhstan | 1,458,470 |
| 7 | Bulgaria | 1,415,924 |
| 8 | Singapore | 660,039 |
| 9 | China | 657,825 |
| 10 | United Kingdom | 399,024 |

---

## 3. 🎯 What they targeted

### Busiest honeypots

| # | Honeypot | What it pretends to be | Events |
|---|---|---|---|
| 1 | P0f | Not a honeypot: guesses attackers' operating systems | 10,258,304 |
| 2 | Suricata | Not a honeypot: network intrusion detection | 6,632,323 |
| 3 | Fatt | Not a honeypot: fingerprints network traffic | 1,693,665 |
| 4 | RDPHoneypot | Windows Remote Desktop | 1,470,086 |
| 5 | Honeytrap | Any unused port | 706,174 |
| 6 | Sentrypeer | Internet phone (SIP) server | 313,937 |
| 7 | Cowrie | SSH and Telnet server | 261,782 |
| 8 | ConPot | Industrial control systems (ICS) | 200,453 |
| 9 | Dionaea | Windows file sharing, SQL, FTP and more | 110,987 |
| 10 | Honeyaml | Fake web API | 38,294 |

### Most-hit ports

| # | Port | Usually used for | Events |
|---|---|---|---|
| 1 | `3389` | Windows Remote Desktop (RDP) | 6,849,666 |
| 2 | `161` | Network device monitoring (SNMP) | 1,159,377 |
| 3 | `5900` | VNC remote screen | 1,069,822 |
| 4 | `5060` | Internet phone calls (SIP) | 658,325 |
| 5 | `445` | Windows file sharing (SMB) | 596,452 |
| 6 | `22` | SSH | 386,284 |
| 7 | `3000` | Web apps and dev servers | 369,198 |
| 8 | `443` | HTTPS websites | 314,115 |
| 9 | `1433` | Microsoft SQL Server database | 196,958 |
| 10 | `53` | DNS | 171,978 |

---

## 4. 🔑 How they tried to get in

### Top passwords

| # | Password | Tries |
|---|---|---|
| 1 | `(blank)` | 376,544 |
| 2 | `123456` | 3,064 |
| 3 | `123` | 2,011 |
| 4 | `1234` | 1,406 |
| 5 | `fff` | 1,262 |
| 6 | `345gs5662d34` | 873 |
| 7 | `3245gs5662d34` | 868 |
| 8 | `password` | 672 |
| 9 | `12345678` | 664 |
| 10 | `1` | 542 |
| 11 | `12345` | 522 |
| 12 | `root` | 453 |
| 13 | `aaaaaa` | 384 |
| 14 | `admin` | 374 |
| 15 | `P@ssw0rd` | 364 |

### Top usernames

| # | Username | Tries |
|---|---|---|
| 1 | `(blank)` | 105,943 |
| 2 | `Administrator` | 102,549 |
| 3 | `administrator` | 56,118 |
| 4 | `admin` | 48,440 |
| 5 | `Systemverwalter` | 16,807 |
| 6 | `Verwalter` | 16,796 |
| 7 | `root` | 14,123 |
| 8 | `user` | 13,755 |
| 9 | `manager` | 12,911 |
| 10 | `sa` | 6,932 |
| 11 | `fff` | 1,262 |
| 12 | `ubuntu` | 1,091 |
| 13 | `345gs5662d34` | 873 |
| 14 | `test` | 493 |
| 15 | `deploy` | 473 |

---

## 5. 🚨 Known attacks (Suricata)

| # | Alert / CVE | Times | What it targets |
|---|---|---|---|
| 1 | SURICATA AF-PACKET truncated packet | 183,289 | Network noise |
| 2 | SURICATA IPv4 truncated packet | 181,920 | Network noise |
| 3 | SURICATA STREAM Packet with broken ack | 116,028 | Network noise |
| 4 | SURICATA STREAM Packet with invalid timestamp | 68,779 | Network noise |
| 5 | SURICATA STREAM spurious retransmission | 55,843 | Network noise |
| 6 | ET INFO SSH session in progress on Expected Port | 6,790 | SSH activity |
| 7 | SURICATA STREAM FIN recv but no session | 5,994 | Network noise |
| 8 | GPL ICMP Destination Unreachable Communication with Destination Host is Administratively Prohibited | 3,440 | Network noise |
| 9 | SURICATA STREAM reassembly sequence GAP -- missing packet(s) | 3,270 | Network noise |
| 10 | SURICATA Applayer Detect protocol only one direction | 2,261 | Network noise |

Most of these alerts are network noise (truncated or messy packets), not real attacks.

---

## 6. ⏰ When

Oct 26: one IP (185.136.15.17, Kazakhstan) ran a full port scan of every port, about 921,000 events, peaking 17:00–19:00 UTC.

---

## 🔎 How I got this data

Searches from [queries](../queries/README.md), run in Kibana Dev Tools against the `logstash-*` indices.
