# Cuckoo Sandbox Configuration

This file documents a safe, repeatable lab configuration for learning malware-analysis workflow concepts. It does not include malware samples.

## 1. Host Preparation

- Use a dedicated analysis machine or isolated VM host.
- Keep the host patched and separate from personal files.
- Create a working folder for reports, sample metadata, and notes.
- Do not enable shared folders unless there is a clear reason.

## 2. Guest Virtual Machine

1. Use VirtualBox to create a disposable Windows or Linux guest.
2. Install only the tools needed for analysis.
3. Install the Cuckoo agent inside the guest.
4. Confirm the guest IP matches `conf/virtualbox.conf`.
5. Take a clean snapshot before any analysis work.

## 3. Network Isolation

Recommended learning setup:

- Host-only network for basic controlled analysis.
- No access to trusted home or work networks.
- Internet access disabled unless a controlled lab exercise requires it.
- DNS and gateway settings documented before every run.

## 4. Snapshot Discipline

Before analysis:

- Start from a known clean snapshot.
- Record the snapshot name in `conf/virtualbox.conf`.
- Verify shared clipboard and drag-and-drop are disabled.

After analysis:

- Export only the report and safe indicators.
- Revert the VM to the clean snapshot.
- Do not keep unknown samples on the host filesystem.

## 5. Configuration Template

`conf/virtualbox.conf` should use placeholders until the local lab values are known:

```ini
[virtualbox]
mode = headless
machines = cuckoo1

[cuckoo1]
label = cuckoo1
platform = windows
ip = <VM_IP_ADDRESS>
snapshot = <SNAPSHOT_NAME>
```

## 6. Analyst Notes to Capture

- Sample hash or safe test-file name.
- VM snapshot used.
- Network mode used.
- Observed file, process, registry, or network indicators.
- Whether the run was blocked, incomplete, or successful.

## Safety Reminder

Only analyze files you are authorized to handle, and only inside an isolated lab. Never run suspicious files directly on a personal or production machine.
