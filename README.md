# 📄 Summary

This report documents a suspected multi-stage malware chain observed on an Android device. The infection appears to begin with a seemingly legitimate app called **Fast Scanner**, which was installed to read PDF documents. Following its installation, two additional apps—**ALL DOCUMENT READER** and **ALL PDF READER**—appeared without direct user consent. These apps exhibit suspicious behavior, including silent installs, spoofed update mechanisms, and system-level anomalies.

---

# Chain of Infection

- **Fast Scanner**  
  Installed manually via Play Store  
  Appears functional and benign  
  May act as a dropper or trigger

- **ALL DOCUMENT READER**  
  Appears shortly after Fast Scanner  
  No installation prompt observed  
  May serve as a bridge or payload loader

- **ALL PDF READER**  
  Claims update access via Play Store  
  Not listed in Play Store search results  
  Behavior suggests spoofing or signature hijacking

---

## System-Level Anomalies

Following the appearance of the suspected malware apps, several system-level anomalies were observed:

- Unexpected system apps appearing post-infection, including:
  - Live Wallpaper Changer  
  - Factory Camera  
  - `com.samsung.input.event`  
  - *(And more unlisted)*

These may be legitimate services that have been cloned, repackaged, or injected with malicious code. Their presence suggests possible use for input monitoring, overlay injection, or permission elevation.

---

## Behavioral Indicators and Ripple Effects

This malware chain does not simply install apps; it creates a behavioral network that affects the entire system:

- Silent installations without user interaction  
- Play Store spoofing (apps claim update access despite being unlisted)  
- Auto-Wi-Fi connections initiated without user action  
- Background activity even when apps are closed  
- Permissions escalation (storage, camera, system settings)  
- Overlay behavior (possibly using Accessibility Services to hijack UI)  
- Persistence tactics (may reappear after deletion or factory reset — untested)  
- App icons and names change or disappear from the launcher  
- Network activity spikes during idle periods  
- Battery drain and overheating without foreground usage  
- Social engineering: apps appear helpful (e.g., PDF readers) while quietly compromising user trust

---

## Device Context

- Mainly affects **Samsung phones**  
- No signs of infection on Google Pixel or other devices  
- Android version: Affected even in latest updates  
- Play Protect: Enabled  
- Infection observed after installing **Fast Scanner** and/or **ALL DOCUMENT READER**

---

## Request for Cleansing of Devices

I am seeking a way to clean the phone from this malware. I would like:

- Confirmation of similar behavior on other devices  
  *(Only if you see Fast Scanner and/or ALL DOCUMENT READER and ALL PDF READER)*

> I do not have the knowledge or skills to reverse engineer malware, especially the Android kind.

---

## Repository

https://github.com/Spl3af

---

## Notes

- This malware uses advanced zero-days and does **not** use Device Admin.  
- If testing, install **Fast Scanner** and **ALL DOCUMENT READER**.  
  - It takes ~1 month for the main payload to install (All PDF Reader)
  - Full behavior may emerge after 0.5 months (possibly waiting for certain conditions)  
- Devices may auto-connect to Wi-Fi even when toggled off due to system-level manipulation.  
  - Believed to be a propagation method for the malware and/or malicious apps.

---

> This report is based purely on firsthand observation.  
> No code was reviewed, but I am confident these apps are malicious—especially **ALL PDF READER**.
