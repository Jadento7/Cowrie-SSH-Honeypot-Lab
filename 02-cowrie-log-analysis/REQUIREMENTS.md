# Requirements

## Prerequisites

Before starting this lab, complete:

```text
01-cowrie-ssh-honeypot
```

You should already have:

- Ubuntu Server VM named `HP01`
- Docker installed
- Cowrie container running
- At least one test SSH login attempt captured
- Cowrie logs available through `docker logs cowrie`

## Hardware Requirements

Recommended host system:

- 8 GB RAM minimum
- 16 GB RAM preferred
- 2 CPU cores available for the Ubuntu honeypot VM
- 25 GB free disk space
- Virtualization enabled in BIOS/UEFI

## Software Requirements

- Oracle VirtualBox
- Ubuntu Server
- Docker
- Cowrie Docker container
- Linux terminal
- Basic command-line tools:
  - `grep`
  - `wc`
  - `ls`
  - `cat`
  - `mkdir`
  - `mv`

## Network Requirements

For this beginner lab:

```text
Testing type: Local controlled test
Cowrie SSH port: 2222
Test target: 127.0.0.1
```

## Log Requirements

Cowrie logs should be exportable with:

```bash
docker logs cowrie > cowrie-session.log
```

Expected log file:

```text
logs/cowrie-session.log
```

## Verification Commands

Export logs:

```bash
docker logs cowrie > cowrie-session.log
```

Find login attempts:

```bash
grep -i "login attempt" logs/cowrie-session.log
```

Find source connections:

```bash
grep -i "New connection" logs/cowrie-session.log
```

Find commands:

```bash
grep "CMD:" logs/cowrie-session.log
```

Count login attempts:

```bash
grep -i "login attempt" logs/cowrie-session.log | wc -l
```

## Safety Requirements

- Do not include real passwords in public documentation
- Do not upload large messy logs without reviewing them
- Do not claim local Docker traffic is a real external attacker
- Do not retaliate against source IPs
- Do not expose the honeypot to the internet unless it is isolated and intentionally designed for that risk
