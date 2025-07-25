# Wireshark Password Capture Lab - Step-by-Step Instructions

## Objective
Capture and analyze plaintext credentials sent over HTTP from a Windows VM to a Kali Linux-hosted login page using Wireshark.

---

## Lab Setup

### 1. Host an HTTP Login Page on Kali Linux

Run these commands on your Kali Linux VM:

```bash
sudo apt update
sudo apt install apache2 -y
sudo mkdir -p /var/www/html/login
echo '<form method="POST"><input name="username" placeholder="Username"><input name="password" type="password" placeholder="Password"><input type="submit"></form>' | sudo tee /var/www/html/login/index.html
sudo systemctl restart apache2
```

This creates a simple, insecure login page accessible at:  
`http://<Kali_IP>/login`

---

### 2. Start Capturing Traffic with Wireshark on Kali

- Launch Wireshark:  
  ```bash
  sudo wireshark
  ```
- Select your network interface (e.g., `eth0`, `enp0s3`)
- Apply the display filter:  
  ```
  http
  ```
- Click the blue shark fin icon to start capturing packets.

---

### 3. Submit Login Credentials from Windows VM

- On your Windows VM, open a browser and visit:  
  ```
  http://<Kali_IP>/login
  ```
- Enter these sample credentials:  
  - Username: `admin`  
  - Password: `password123`
- Submit the form.

---

### 4. Stop Packet Capture and Save the File

- Return to Wireshark on Kali  
- Click the red square icon to stop capture  
- Save the capture file as:  
  ```
  pcaps/http-password-capture.pcapng
  ```

---

### 5. Analyze Captured Traffic in Wireshark

- In Wireshark, apply this filter to isolate the POST request:  
  ```
  http.request.method == "POST"
  ```
- Select the POST packet and expand the details pane to find the submitted credentials (`username=admin` and `password=password123`) in the HTTP payload.

---

### 6. Taken Screenshots

- Screenshot the login page on Windows VM (`screenshots/windows-vm-login-screen.png`)
- Screenshot the HTTP POST payload with credentials visible (`screenshots/wireshark-captured-credentials.png`)

---

