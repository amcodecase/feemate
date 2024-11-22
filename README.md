# **FeeMate - WhatsApp-Based Fee Payment System**

**FeeMate** is a simple, secure, and user-friendly fee payment system that enables students at Zambian universities and colleges to pay their fees using **Mobile Money** (MTN MoMo, Airtel Money) via **WhatsApp**. The entire process, from checking fees to confirming the payment, happens within WhatsApp until the student needs to authorize the payment with their **Mobile Money PIN** via **USSD**. After entering the PIN, the student receives payment confirmation in WhatsApp.

---

## **Overview**

FeeMate integrates **WhatsApp** and **USSD** to provide a seamless fee payment experience. Students interact with a **WhatsApp bot** to initiate payments and receive updates. When it's time to authorize the payment, the bot triggers a **USSD code** to facilitate **Mobile Money** transactions. No internet connection is required for the PIN entry as it’s done via USSD. Once the payment is completed, the student is notified in WhatsApp.

---

## **Features**

- **WhatsApp Integration**: Students interact with the WhatsApp bot to check fees, initiate payments, and get updates.
- **USSD Payment Authorization**: Payments are authorized through USSD by entering the **Mobile Money PIN** on the student's phone (no internet required).
- **Mobile Money Payment**: Supports payment via **MTN MoMo** and **Airtel Money** using USSD codes.
- **Seamless Experience**: The entire fee payment process happens within WhatsApp until the PIN entry.
- **Secure Transactions**: PINs are never stored; they are only used temporarily during the USSD process.
- **Payment Confirmation**: Once the payment is processed, the bot sends confirmation via WhatsApp.

---

## **How It Works**

1. **Student Initiates Payment via WhatsApp**:
   - The student sends a message to the **FeeMate bot** on WhatsApp to check their fee balance or initiate a payment.
   - The bot confirms the payment amount and asks the student to choose a payment method (e.g., MTN MoMo or Airtel Money).

2. **Payment Authorization via USSD**:
   - The student selects a payment method, and the bot sends a USSD request (e.g., *232# for MTN MoMo) to initiate the payment.
   - The student enters their **Mobile Money PIN** via USSD on their mobile phone to authorize the payment (no internet required for this step).

3. **Payment Confirmation**:
   - The payment process is completed by the mobile network, and the backend receives confirmation.
   - The bot sends a **payment confirmation** to the student via WhatsApp.

4. **Transaction Record**:
   - All transaction details (amount, student ID, payment reference) are saved in the backend for record-keeping and reporting.

---

## **Tech Stack**

- **Frontend**:
  - **WhatsApp Business API** (via Twilio/MessageBird) for handling communication with students.

- **Backend**:
  - **Node.js (Express)** or **Python (Flask/Django)** to manage payment requests, trigger USSD, and communicate with WhatsApp.
  
- **USSD Gateway**:
  - Integration with **MTN MoMo** or **Airtel Money** USSD API for payment authorization via USSD.

- **Database**:
  - **MySQL/PostgreSQL** to store transaction data and student records.

- **Security**:
  - **SSL/TLS encryption** for secure communication.
  - **PIN Handling**: Mobile Money PINs are never stored or transmitted in plaintext.

---

## **Installation**

### **1. Prerequisites**
Ensure you have the following installed:
- **Node.js** (for Express) or **Python** (for Flask/Django).
- **MySQL/PostgreSQL** for the database.
- **WhatsApp Business API** access (via Twilio/MessageBird).
- **Mobile Money API** access (MTN MoMo, Airtel Money).

### **2. Clone the Repository**

```bash
git clone https://github.com/yourusername/feemate.git
cd feemate
```

### **3. Backend Setup**

#### **For Node.js (Express)**

1. Install dependencies:

   ```bash
   npm install
   ```

2. Set up environment variables in `.env`:

   ```env
   WHATSAPP_API_KEY=your_whatsapp_api_key
   MOBILE_MONEY_API_KEY=your_mobile_money_api_key
   DB_HOST=your_database_host
   DB_USER=your_database_user
   DB_PASS=your_database_password
   DB_NAME=your_database_name
   ```

3. Start the server:

   ```bash
   npm start
   ```

#### **For Python (Flask/Django)**

1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Set up environment variables in `.env` (same as Node.js setup).

3. Start the server:

   ```bash
   python app.py  # Flask
   python manage.py runserver  # Django
   ```

---

## **Usage**

1. **Start the Conversation**: Students message the **FeeMate bot** on WhatsApp to check their fees or initiate a payment.

2. **Payment Process**: After the student selects a payment method (e.g., MTN MoMo or Airtel Money), the bot triggers a USSD code.

3. **USSD Payment Authorization**: The student enters their **Mobile Money PIN** via USSD on their phone. This step requires no internet.

4. **Confirmation via WhatsApp**: Once the payment is processed, the bot sends a **payment confirmation** back to the student on WhatsApp.

---

## **Security**

- **SSL/TLS Encryption**: All communication between WhatsApp and the backend is encrypted.
- **PIN Handling**: PINs are never stored. They are only temporarily used during the USSD process and not stored on the backend.
- **Transaction Logging**: All transactions are logged for transparency and to ensure accountability.

---

## **Challenges & Limitations**

- **USSD Reliability**: USSD transactions depend on mobile network availability and can sometimes experience delays or failures.
- **PIN Security**: Ensuring the secure handling of PINs is critical to prevent unauthorized access or fraud.

---

## **Future Enhancements**

- **Multi-Currency Support**: Expand the system to support international students or multi-currency payments.
- **Mobile App Integration**: A dedicated mobile app for students to manage and pay fees.
- **Admin Dashboard**: Build a dashboard for administrators to monitor transactions and generate reports.

---

## **License**

This project is licensed under the **MIT License** - see the [LICENSE.md](LICENSE.md) file for details.

---

## **Contributing**

Feel free to fork the repository and submit pull requests for improvements or bug fixes. Contributions are welcome!

---

**Contact**:  
For any inquiries, contact the project maintainer at [info@natec.icu].

---
