
touch CONFIGURATION.md

# Cuckoo Sandbox Configuration

## Step 1: Set Up Virtual Machine

1. Use VirtualBox to create a VM with Windows or Linux.
2. Install the VirtualBox Guest Additions on the VM.
3. Install Python and the Cuckoo agent on the VM:
   ```bash
   pip install pycrypto
   wget https://github.com/cuckoosandbox/cuckoo/raw/master/agent/agent.py
   python agent.py
