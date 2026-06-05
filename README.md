# ODL-Path-Traversal (CVE-2026-36500)

We tested this bug against OpenDayLight 12.0.5. 

This bug was found by analyzing the source code of the controller using an AI coding agent (Claude). 

### Attack Description:

An issue in the cluster-admin:backup-datastore component of ODL Controller v12.0.5 allows a remote attacker to perform a path traversal via a crafted request.

### Attack Vectors:
Exploitable via RESTCONF HTTP POST over the network.

### Impact:
Attackers can write arbitrary files to any location accessible by the ODL process.

### Recommended Fix:
Validate and restrict the file-path parameter to a permitted base directory and reject any path that resolves outside it.
