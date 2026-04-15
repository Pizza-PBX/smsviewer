# 🚀 VoIP SMS Gateway for BulkVS & Flowroute

A lightweight PHP integration designed to handle SMS webhooks for PBX systems (FreePBX/Asterisk). This setup allows you to receive and process SMS messages by routing webhooks from your provider directly to your server.

---

### 📂 Installation & Server Setup

Run these steps in your terminal to configure the web directory and set appropriate permissions.

**Terminal Commands:**
1. cd /var/www/html
2. mkdir sms
3. cd sms
4. (Upload the 8 .php files here)
5. nano config.php
6. nano login.php
7. chown -R asterisk:asterisk /var/www/html/sms
8. chmod -R 775 /var/www/html/sms

---

### 🌐 Provider Configuration (BulkVS)

Follow these steps inside your BulkVS portal to link your DID to the gateway.

1.  **Create Message Webhook:**
    * Navigate to **Message Webhooks**.
    * Add a new webhook URL pointing to your server: 
        `http://<YOUR_PBX_IP>/sms/pizza.php`
2.  **Firewall Configuration:**
    * Whitelist the BulkVS IPs to ensure the webhook reaches your server. 
    * **Common IPs:** `52.206.134.245` or `192.9.236.42`
3.  **DID Mapping:**
    * Go to **DIDs -> Manage**.
    * Select your DID and click **View**.
    * Set **Messaging Webhook** to the name created in Step 1.
    * Ensure **Enable SMS** is checked.
    * Select your **Trunk Group** (configured under Interconnection).

---

### 💡 Alternative Providers

* **Flowroute:** This setup is fully compatible. Refer to Flowroute's documentation for their specific API callback format and ensure their signaling IPs are unblocked in your firewall.

---

> **Note:** Ensure your PBX firewall (System Admin -> Firewall in FreePBX) is configured to allow traffic on Port 80/443 from your provider's IP range.
