# Metasploitable 2 — OVA

A pre-built [Metasploitable 2](https://docs.rapid7.com/metasploit/metasploitable-2/) virtual appliance packaged as an **OVA**, ready to import into **VirtualBox** or **VMware**. Metasploitable is an intentionally vulnerable Linux virtual machine published by Rapid7 for practising penetration testing, exploit development, and security training in a safe, disposable lab.

The appliance is distributed on the [**Releases**](../../releases) page because it is too large for the normal repository file size limits.

---

> ## ⚠️ Security warning — this VM is deliberately insecure
>
> Metasploitable ships with weak passwords, backdoored services, and known-vulnerable software **on purpose**. Anyone who can reach it on the network can fully compromise it in minutes.
>
> - **Never** expose it to the public internet or any untrusted/production network.
> - Run it only on an isolated **Host-only** or **NAT** network.
> - Treat it as throwaway — snapshot before you start and roll back when done.

---

## Download

Download the appliance from the [**Releases**](../../releases) page:

| File | Size | SHA-256 |
|------|------|---------|
| `Metasploitable.ova` | ~893 MB | `4CF5261E402F9BAA7CEC11CD3CC57E071639162FDC8FF9C6B60B25B90475B4C7` |

### Verify the download

**Windows (PowerShell):**

```powershell
Get-FileHash .\Metasploitable.ova -Algorithm SHA256
```

**Linux / macOS:**

```bash
sha256sum Metasploitable.ova        # Linux
shasum -a 256 Metasploitable.ova    # macOS
```

The output must match the SHA-256 above. If it doesn't, re-download — do not run a tampered image.

---

## Import

### VirtualBox

1. **File → Import Appliance…**
2. Select `Metasploitable.ova` and click **Next**.
3. Review the settings (defaults are fine) and click **Import**.
4. Before first boot, open the VM's **Settings → Network** and set the adapter to **Host-only Adapter** (or NAT).

### VMware Workstation / Player / Fusion

1. **File → Open…**
2. Select `Metasploitable.ova`, choose a name/location, and accept any conversion prompt.
3. Set the network adapter to **Host-only** before powering on.

---

## First login

| | |
|---|---|
| **Username** | `msfadmin` |
| **Password** | `msfadmin` |

The same credentials work for SSH. Use `sudo` for root. (Several other accounts and services have intentionally weak/default credentials too.)

---

## What's inside

- Based on **Ubuntu 8.04** (Linux 2.6 kernel) — end-of-life by design.
- Runs a wide range of intentionally vulnerable and misconfigured services, e.g. FTP (vsftpd), Telnet, SSH, SMTP, HTTP, Samba, MySQL, PostgreSQL, VNC, distcc, UnrealIRCd, Tomcat, and the DVWA / Mutillidae web apps.
- Great for practising scanning, enumeration, exploitation, and post-exploitation with tools like Nmap, Metasploit, and Hydra.

See Rapid7's [Metasploitable 2 Exploitability Guide](https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/) for a walkthrough of the services and known vulnerabilities.

---

## Credits & source

Metasploitable 2 is created and published by [Rapid7](https://www.rapid7.com/). This repository only **repackages** the original VM as an OVA for convenient import; no part of the vulnerable system was modified. All trademarks and rights belong to their respective owners.

## License

Use of Metasploitable is subject to the terms set by Rapid7. This repository claims no ownership over the Metasploitable software and provides the image **as-is, for lawful security education and testing only**. You are responsible for how you use it.
