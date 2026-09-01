# Task 3 – Basic Vulnerability Scan

## Objective

To perform a basic vulnerability scan on my local computer and identify common security issues using Nessus Essentials.

## Tool Used

- Nessus Essentials
- Scan Policy: Basic Network Scan
- Target: 127.0.0.1 (Localhost)

## Scan Summary

| Detail | Result |
|---|---|
| Scan Name | Task 3 - Basic Vulnerability Scan |
| Target | 127.0.0.1 |
| Scan Type | Basic Network Scan |
| Status | Completed |
| Scan Duration | 7 minutes |
| Total Findings | 23 |
| Critical | 0 |
| High | 0 |
| Medium | 1 |
| Low | 0 |
| Informational | Remaining findings |

## Most Important Finding

### SSL Certificate Cannot Be Trusted

- Severity: Medium
- CVSS Score: 6.5
- Host: 127.0.0.1
- Port: 8834/TCP

### Description

Nessus reported that the SSL certificate used by the service could not be verified through a trusted certificate chain. This can happen when a certificate is self-signed, expired, or not signed by a recognized Certificate Authority.

### Recommended Mitigation

For production or externally accessible services, use a valid certificate issued by a trusted Certificate Authority or an appropriate internal CA. Verify the certificate chain, hostname, and validity period.

Since this scan was performed against 127.0.0.1 and port 8834, the finding is associated with the locally running Nessus web service and does not by itself indicate that the computer has been compromised.

## Informational Findings

Nessus also detected several informational items, including:

- Microsoft Windows SMB/CIFS service information on port 445.
- SMBv2 and supported SMB dialect information.
- NetBIOS/SMB system information.
- Local Nessus web server (NessusWWW) information on port 8834.
- HTTP protocol information.
- TLS 1.2 service detection.
- TLS supported groups information.

These findings were informational and were not reported as Critical, High, or Low vulnerabilities.

## Security Recommendations

1. Keep Windows and installed applications updated.
2. Use trusted SSL/TLS certificates for production services.
3. Restrict SMB/port 445 access using Windows Firewall when it is not required.
4. Disable unnecessary network services.
5. Perform vulnerability scans periodically.
6. Investigate and prioritize Medium, High, and Critical findings first.

## Conclusion

A basic vulnerability assessment was successfully performed on the local computer using Nessus Essentials.

The scan completed successfully and identified 23 findings, with 1 Medium-severity finding and no Critical or High-severity vulnerabilities. The main finding was an untrusted SSL certificate associated with the locally running service. The remaining reviewed findings were informational.
