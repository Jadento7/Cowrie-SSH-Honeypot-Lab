# Cowrie Log Analysis Summary

## Overview

This analysis reviews SSH honeypot activity captured by Cowrie during a controlled local test.

## Key Findings

| Category | Finding |
|---|---|
| Honeypot service | Cowrie SSH |
| Port | 2222 |
| Test username | root |
| Test password | jadento7, password123, aa, a |
| Source IP | 172.17.0.1 |
| Result | Cowrie accepted the login into a fake shell |
| Commands captured | whoami, id, uname -a, ls, cat /etc/passwd, exit |

## Metrics

| Metric | Count |
|---|---:|
| SSH connections | 4 |
| Login attempts | 4 |
| Commands captured | 9 |

## Notes

The source IP is from local Docker networking because this was a controlled local lab. This was not a real internet attacker.

Cowrie intentionally accepted the fake login and placed the session into a simulated shell so activity could be captured safely.
