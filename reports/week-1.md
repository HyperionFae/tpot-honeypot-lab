# 📊 Findings Report: Week 1

**Dates covered:** Oct 14, 2026 to Oct 18, 2026

**Written by:** HyperionFae

---

## ⭐ Headline

The passwords everyone is told never to use, like 123456, password and admin, are still being tried thousands of times a day, because they still work somewhere.

---

## 1. 📈 The numbers

### Events per day

| Day | Events | Storage | Notes |
|---|---|---|---|
| Oct 14 | 1,019,502 | 415 MB | Only ~6 hours online |
| Oct 15 | 2,021,034 | 972 MB | Busiest day |
| Oct 16 | 1,535,139 | 661 MB |  |
| Oct 17 | 1,851,123 | 751 MB |  |
| Oct 18 | 1,487,409 | 668 MB |  |

| Stat | Value |
|---|---|
| Total events | 7,914,207 |
| Busiest day | Oct 15 (2,021,034 events) |
| Files captured | 21 (18 WannaCry, 3 SSH backdoor files) |

---

## 2. 🔑 How they tried to get in

### Top passwords

| # | Password | Tries |
|---|---|---|
| 1 | `(blank)` | 118,454 |
| 2 | `123456` | 791 |
| 3 | `password` | 315 |
| 4 | `1234` | 308 |
| 5 | `123` | 295 |
| 6 | `3245gs5662d34` | 239 |
| 7 | `345gs5662d34` | 237 |
| 8 | `12345` | 200 |
| 9 | `12345678` | 200 |
| 10 | `linuxshell` | 187 |
| 11 | `sh` | 187 |
| 12 | `admin` | 168 |
| 13 | `root` | 145 |
| 14 | `1` | 132 |
| 15 | `P@ssw0rd` | 107 |

### Top usernames

| # | Username | Tries |
|---|---|---|
| 1 | `Administrator` | 63,443 |
| 2 | `(blank)` | 42,388 |
| 3 | `sa` | 10,361 |
| 4 | `admin` | 7,551 |
| 5 | `user` | 4,879 |
| 6 | `root` | 4,526 |
| 7 | `administrator` | 1,350 |
| 8 | `ubuntu` | 324 |
| 9 | `345gs5662d34` | 237 |
| 10 | `Admin` | 229 |
| 11 | `system` | 192 |
| 12 | `test` | 189 |
| 13 | `enable` | 187 |
| 14 | `postgres` | 172 |
| 15 | `deploy` | 96 |

---

## 3. 🦠 Malware captured

| # | SHA-256 | Times seen | VirusTotal verdict | Write-up link |
|---|---|---|---|---|
| 1 | `a8460f446be5` | 1 | mdrfckr SSH backdoor (Outlaw / Dota botnet) | [Read the write-up](../malware/mdrfckr-ssh-backdoor.md) |

---

## 4. 🚨 Known attacks (Suricata)

| # | Alert / CVE | Times | What it targets |
|---|---|---|---|
| 1 | CVE-2017-0147 (EternalBlue / MS17-010) | 18 | Windows file sharing (SMBv1) |

---

## 5. 🧠 My thoughts

### What surprised me

1. The passwords everyone is told never to use are still being tried and still work somewhere

### What I learned

1. Once something is exposed to the internet, a lot happens to it straight away, even if you can't see it: my honeypot logged over 1 million events in its first 6 hours online.

---

## 🔎 How I got this data

Searches from [queries](../queries/README.md), run in Elasticvue against the `logstash-*` indices.
