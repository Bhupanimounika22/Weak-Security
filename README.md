 # 🛡️ Understanding "Weak Security" in Wi-Fi (macOS, iOS)

If you use macOS or iOS, you may have seen a **"Weak Security"** warning under your Wi-Fi network.  
This happens when your router uses **outdated Wi-Fi encryption** (like WPA, TKIP, or WEP).  

---

## 🔍 Why does this happen?

- **WEP** → Very old, easily hackable.  
- **WPA (TKIP)** → Better than WEP but still insecure today.  
- **WPA/WPA2 Mixed Mode** → Allows both WPA (insecure) and WPA2 (secure). Apple flags this as *weak*.  
- **WPA2 (AES only)** → Secure, recommended if WPA3 is not available.  
- **WPA3 (AES)** → Latest and most secure option.  

👉 If your router is set to **WPA/WPA2 mixed mode**, Apple devices will show *Weak Security* even if WPA2 is being used.

---

## ⚡ Example: Airtel GPON Router

On Airtel GPON Home Gateways, Wi-Fi settings often look like this:

- **Encryption Mode** → WPA/WPA2 Personal  
- **WPA Version** → WPA/WPA2 (no WPA2-only option)  
- **WPA Encryption Mode** → TKIP/AES  

### Problem:
- WPA/WPA2 mode = weak (because WPA is still allowed).  
- TKIP = insecure (AES should be used instead).  

---

## ✅ How to Fix

1. **Log in to your router**  
   - Open a browser and go to your router IP (usually `192.168.1.1`).
     
2. Go to **Network → Wireless (2.4GHz / 5GHz)**.  

3. Change settings:
   - **Security Mode** → WPA/WPA2 Personal (best available on Airtel).  
   - **Encryption** → AES only (disable TKIP).  
   - **Password** → Use at least 12 characters (mix of letters, numbers, symbols).  

4. Save & reboot router.  

5. Forget and reconnect Wi-Fi on your devices.  

---

## ⚠️ Limitations on Airtel GPON

- No **WPA2-only** option → router forces WPA/WPA2 mixed mode.  
- This means Apple devices **will still show "Weak Security"** warning.  
- The only permanent fix:  
  - Connect your **own Wi-Fi router** (TP-Link, Asus, Netgear, etc.) to the Airtel ONT.  
  - Configure it with **WPA2-PSK (AES)** or **WPA3**.  
  - Disable Wi-Fi on the Airtel GPON.

---

## 📌 Recommendations

- Always prefer **WPA3** (if supported).  
- Otherwise, use **WPA2-PSK (AES only)**.  
- Avoid **WEP, WPA, TKIP, or mixed modes**.  
- Disable **WPS** for extra security.  
- Use a strong Wi-Fi password.  

🔒 **In short:** If your router allows only **WPA/WPA2 mixed mode**, your Wi-Fi is still secure with AES, but macOS will complain.  
For best security → **use your own router with WPA2/WPA3**.  
