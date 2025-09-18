# 🖥️ Windows Virtual PC (GitHub Actions)

This project lets you boot up a **Windows virtual computer** inside GitHub Actions with:

- ✅ **UEFI Boot (OVMF)**
- ✅ **4 CPU Cores**
- ✅ **12 GB RAM**
- ✅ **256 GB Virtual Disk**
- ✅ **Remote Access via Tailscale + VNC**
- ⏳ Runs for **5 hours** per session

---

## 🚀 How to Use

1. **Fork this repository** (or copy the workflow into your own repo).  

2. **Set up your Tailscale Auth Key**  
   - Go to [Tailscale Admin Console](https://login.tailscale.com/admin/settings/keys)  
   - Generate an **Auth Key**  
   - In your repo, go to **Settings → Secrets and variables → Actions → New repository secret**  
   - Name it: `TAILSCALE_AUTHKEY`  
   - Paste your Auth Key  

3. **Run the Workflow**  
   - Go to **Actions tab → Windows-VirtualPC → Run workflow**  
   - Paste the **direct download link of a Windows ISO** in the input box  

   Example ISO links:  
   - Windows 10 Lite (19H2 x64):  
     ```
     https://archive.org/download/windows-10-lite-edition-19h2-x64/Windows%2010%20Lite%20Edition%2019H2%20x64.iso
     ```
   - Windows 11 Pro (Official MS ISO):  
     ```
     https://software-download.microsoft.com/pr/Win11_23H2_English_x64v2.iso
     ```

   ⚠️ The ISO link **must be direct download** (ending with `.iso`).

4. **Connect to Your Virtual PC**
   - After the workflow starts, wait ~2–3 minutes  
   - The job logs will show your **Tailscale IP**  
   - Open **RealVNC Viewer** (or any VNC client)  
   - Connect to:  
     ```
     <TAILSCALE-IP>:5900
     ```  
   - No password is required  

---

## 🛠️ Specs

- CPU: **4 Cores (qemu64)**
- RAM: **12 GB**
- Disk: **256 GB (qcow2)**
- Boot: **UEFI (OVMF)**
- Network: **Tailscale VPN**
- Remote: **VNC (port 5900)**

---

## ⏳ Session Time

- Each session runs for **5 hours (300 minutes)**  
- After that, the VM shuts down automatically  

---

## ⚡ Notes

- This setup is **for testing / educational purposes only**.  
- Performance is limited by GitHub Actions hardware.  
- If you need persistent storage, you must **download the disk image** (`windows_disk.qcow2`) before the job ends.  

---

### 🏁 Enjoy your free Windows Virtual PC in the cloud!
