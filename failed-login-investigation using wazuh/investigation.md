# SOC-001 — Investigation

## 1. Alert Summary

- Alert: Windows Failed Logon
- Event ID: 4625
- Severity: Under Investigation
- Host: sys2
- Target Account: CISCO
- Source Device: another_vm
- Source IP: 192.168.65.141
- Failed Attempts: 1

## 2. Initial Assessment

A Windows failed-logon event (Event ID 4625) was detected on the
Windows Server host.

The event indicates that an authentication attempt failed for the
account `CISCO`.

The source was identified as `another_vm`.

## 3. Investigation Performed

### Step 1 — Validate the Alert

- Confirmed Event ID 4625 in Wazuh.
- Confirmed the affected host.
- Confirmed the target username.
- Confirmed the source device/IP.

### Step 2 — Check for Successful Authentication

A corresponding Windows Event ID 4624 was identified.

- Matching 4624: Yes
- Result: Successful authentication observed after the failed attempt.

### Step 3 — Determine Source

- Source Device: another_vm
- Source IP: 192.168.65.141

The source should be reviewed to determine whether the authentication
attempt was expected.

## 4. Evidence

See `evidence.md` for the collected Wazuh and Windows Event Viewer
evidence.

## 5. Current Assessment

Status: Under Investigation

The failed authentication alone does not establish malicious activity.
Additional context is required to determine whether the activity was
legitimate or suspicious.

## 6. Recommended Next Investigation

- Review the Event ID 4625 authentication details.
- Review the corresponding Event ID 4624.
- Check the source system for additional failed logons.
- Check whether multiple accounts were targeted.
- Check the time sequence between 4625 and 4624.
- Review related Wazuh alerts for the same source IP.
- Escalate if repeated or suspicious authentication activity is found.

## 7. Conclusion

Investigation is currently in progress.

The available evidence confirms a failed authentication attempt
followed by a successful authentication event. No conclusion of
malicious activity has been made based solely on this evidence.
