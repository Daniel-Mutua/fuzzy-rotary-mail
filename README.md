[README.md](https://github.com/user-attachments/files/24188867/README.md)

# ESP32 Email Sender Using ReadyMail

This project demonstrates how to send an email from an **ESP32** using **Wi‑Fi** and the **ReadyMail** library.  
It connects the ESP32 to a Wi‑Fi network, authenticates with an SMTP server, and sends a test email to a specified recipient.

---

## 📌 Features

- Connects ESP32 to Wi‑Fi
- Sends email using SMTP over SSL (port 465)
- Supports plain text email messages
- Optional file attachment support via SD card
- Debug output via Serial Monitor

---

## 🧰 Hardware Requirements

- ESP32 development board  
- USB cable  
- (Optional) SD card module for attachments  

---

## 📚 Software Requirements

- Arduino IDE (latest version recommended)
- ESP32 board support package installed
- **ReadyMail** library (installed via Arduino Library Manager)

---

## 📦 Required Libraries

Install the following libraries from **Arduino IDE → Library Manager**:

- `WiFi` (comes with ESP32 core)
- `ReadyMail`

Optional (for attachments):
- `SD`

---

## ⚙️ Configuration

Edit the following fields in the code before uploading:

### Wi‑Fi Credentials
```cpp
const char* ssid     = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";
```

### Email / SMTP Settings
```cpp
const char* smtp_server = "smtp.example.com";
const int   smtp_port   = 465;
const char* email_user  = "sender@example.com";
const char* email_pass  = "YOUR_EMAIL_PASSWORD";
const char* recipient   = "recipient@example.com";
```

> ⚠️ **Note:**  
> - Use an **App Password** if your email provider requires it (e.g., Gmail).
> - Ensure SMTP access is enabled for your email account.

---

## 🚀 How It Works

1. ESP32 connects to the specified Wi‑Fi network.
2. ReadyMail initializes an SMTP session.
3. A test email is created with subject and message body.
4. The email is sent to the recipient.
5. Status messages are printed on the Serial Monitor.

---

## ▶️ Usage

1. Open the Arduino IDE.
2. Select the correct **ESP32 board** and **COM port**.
3. Upload the sketch to the ESP32.
4. Open the Serial Monitor at **115200 baud**.
5. Wait for the message:
   ```
   Email sent successfully!
   ```

---

## 📎 Optional: Email Attachments

To attach a file from an SD card:

1. Uncomment the SD library:
```cpp
#include <SD.h>
```

2. Initialize SD card and add attachment:
```cpp
message.addAttachment("/test.txt");
```

Ensure the file exists on the SD card.

---

## 🐞 Troubleshooting

- **Wi‑Fi not connecting**  
  → Double‑check SSID and password.

- **Email not sent**  
  → Verify SMTP server, port, and credentials.

- **Authentication error**  
  → Use App Password instead of normal email password.

- **No serial output**  
  → Confirm baud rate is set to 115200.

---

## 📄 License

This project is provided for **educational purposes**.  
You are free to modify and use it in your own ESP32 projects.

---

## ✉️ Example Output

```
Connecting to Wi‑Fi...
Wi‑Fi connected!
Email sent successfully!
```

---

Happy coding 🚀
