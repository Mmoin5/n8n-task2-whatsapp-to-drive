## WhatsApp to Google Drive Automation (n8n Workflow)

This project automates the process of receiving media files via **WhatsApp**, saving them to **Google Drive**, and sending a confirmation message back to the sender — using **n8n** and **Twilio API**.

## ✅ Features

- Trigger workflow when a media message is received on WhatsApp via Twilio.
- Automatically download the media file.
- Upload it to your Google Drive.
- Send a confirmation WhatsApp reply to the sender.

## 🧰 Tech Stack

- [n8n](https://n8n.io) (Self-hosted)
- Twilio WhatsApp API
- Google Drive API

## 📦 Workflow Nodes

1. **Twilio Trigger**
   - Listens for incoming WhatsApp media messages.
   - Requires webhook URL configured in Twilio console.

2. **HTTP Request (Download Media)**
   - Fetches the media file from the Twilio-provided media URL.
   - Uses Twilio Basic Auth for authentication.

3. **Google Drive (Upload File)**
   - Uploads the downloaded media to the root folder of your Google Drive.
   - Filenames are dynamically named based on the sender ID and timestamp.

4. **HTTP Request (Reply via Twilio)**
   - Sends an automated confirmation message back to the user on WhatsApp.
   - Uses Twilio’s API with Basic Auth.

## 🔐 Environment Variables (Recommended)

Avoid hardcoding sensitive information. Use environment variables like:

TWILIO_ACCOUNT_SID=ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
TWILIO_AUTH_TOKEN=your_auth_token

## 🛠 Setup Instructions

1. Clone the Repository
   git clone https://github.com/<your-username>/n8n-task2-whatsapp-to-drive.git
   cd n8n-task2-whatsapp-to-drive

2. Install Dependencies
   npm install

3. Start n8n
   If globally installed:
   n8n

   Or via npx:
   npx n8n

4. Import Workflow
   
   I   Open http://localhost:5678

   II  Click the hamburger menu → Workflows → Import workflow

   III Choose the My workflow.json file

   IV  Configure credentials:

     i)  Twilio (Account SID + Auth Token)

     ii) Google Drive (OAuth2)

5. Set Webhook in Twilio
Paste the Test Webhook URL from n8n into:
Twilio Console → Messaging → WhatsApp Sandbox → When a message comes in → POST → <your n8n webhook URL>


## 📁 Project Structure

n8n-task2/

├── node_modules/

├── package.json

├── package-lock.json

└── My workflow.json


## 👨‍💻 Author
Name: Mohammed Moin Pasha

Gmail: mmoinpasha500@gmail.com

## 🛡️ License
**This project is for educational purposes only. Do not share real credentials publicly.**
