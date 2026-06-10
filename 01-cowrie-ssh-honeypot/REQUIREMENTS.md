# Requirements

## Hardware Requirements

Recommended host system:

- 8 GB RAM minimum
- 16 GB RAM preferred
- 2 CPU cores available for the honeypot VM
- 25 GB free disk space
- Virtualization enabled in BIOS/UEFI

## Software Requirements

- Oracle VirtualBox
- Ubuntu Server ISO
- Docker
- SSH client
- Terminal access
- Screenshot tool

## VM Requirements

Recommended VM settings:

```text
VM Name: HP01
OS: Ubuntu Server
RAM: 2048 MB minimum
CPU: 2
Disk: 25 GB minimum
Network: NAT for safe local testing
```

## Docker Requirements

Docker should be installed and running.

Verification commands:

```bash
docker --version
docker ps
```

## Cowrie Requirements

Cowrie is deployed using Docker.

Image:

```text
cowrie/cowrie
```

Run command:

```bash
docker run -d --name cowrie -p 2222:2222 -p 2223:2223 cowrie/cowrie
```

## Network Requirements

For the beginner version of this lab:

```text
Network Mode: NAT
Test Target: 127.0.0.1
SSH Port: 2222
```

Test command:

```bash
ssh root@127.0.0.1 -p 2222
```

## Safety Requirements

- Use fake test passwords only
- Do not store personal files on the honeypot
- Do not expose the honeypot directly to the public internet for this beginner lab
- Do not use real SSH keys
- Do not retaliate against any IP addresses
- Shut down the VM when not in use

## Verification Commands

Check Cowrie is running:

```bash
docker ps
```

Check logs:

```bash
docker logs cowrie
```

Optional log export:

```bash
docker logs cowrie > cowrie-session.log
```
