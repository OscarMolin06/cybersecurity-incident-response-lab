# Incident Analysis Report #01

**Analyst:** Oscar Molina  
**Incident Type:** SSH Brute-Force Attack / Unauthorized Access Attempt  
**Severity Level:** Medium  

## 1. Summary
During routine log review of authentication services (/var/log/auth.log), multiple failed authentication attempts were detected targeting standard high-privilege system accounts (admin, root) originating from internal IP address `192.168.1.105`.

## 2. Event Timeline
**00:14:20** - Authorized connection established from legitimate workstation 192.168.1.50.
**00:14:22 - 00:14:31** - High-frequency authentication failures observed from 192.168.1.105 over non-standard source ports.
**00:14:35** - Session terminated prior to successful authentication.

## 3. Impact Assessment
No system compromise was achieved. However, the activity indicates internal network reconnaissance or credential stuffing behavior.

