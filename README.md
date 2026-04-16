# 💱 Currency Converter Webhook (Flask + Dialogflow)

A Flask-based webhook integration for a Dialogflow chatbot that performs real-time currency conversions. When a user requests a conversion, the webhook processes the input, fetches the latest exchange rates from an external API, and returns the converted value back to Dialogflow.

---

## 🚀 Features

- 🔁 Convert between any two world currencies  
- 🌐 Real-time exchange rates using external API  
- 🤖 Seamless integration with Dialogflow chatbot  
- 🪝 JSON responses formatted for Dialogflow (`fulfillmentText`)  
- ⚡ Fast and lightweight Flask backend  

---

## 🧠 How It Works

1. User sends a query to Dialogflow (e.g., *"Convert 100 USD to INR"*)  
2. Dialogflow extracts parameters (amount, source currency, target currency)  
3. Webhook (Flask server) receives the request  
4. Fetches live exchange rate using an API  
5. Returns the converted result to Dialogflow  

---

## 🧑‍💻 Technologies Used

- Python 3.x  
- Flask – Lightweight web framework  
- requests – For API calls  
- Dialogflow – NLP and intent handling  

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/currency-converter-webhook.git
cd currency-converter-webhook
```

### 2. Create Virtual Environment (Optional but Recommended)

```bash
python -m venv venv
```

Activate it:

- **Windows**
```bash
venv\Scripts\activate
```

- **Linux / macOS**
```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Application

```bash
python app.py
```

The Flask server will start at:

```
http://127.0.0.1:5000
```

---

## 🔗 Dialogflow Webhook Setup

1. Go to Dialogflow Console  
2. Navigate to **Fulfillment**  
3. Enable **Webhook**  
4. Provide your webhook URL (use ngrok for local testing)  

Example:
```bash
ngrok http 5000
```

Paste the generated HTTPS URL into Dialogflow.

---

## 📂 Project Structure

```
currency-converter-webhook/
│── app.py
│── requirements.txt
│── README.md
```

---

## 📤 Sample Request (Dialogflow → Webhook)

```json
{
  "queryResult": {
    "parameters": {
      "unit-currency": {
        "currency": "USD"
      },
      "currency-name": "INR",
      "number": 100
    }
  }
}
```

---

## 📥 Sample Response (Webhook → Dialogflow)

```json
{
  "fulfillmentText": "100 USD is equal to 8300 INR"
}
```

---

## ✨ Future Improvements

- 📊 Add historical exchange rate charts  
- 🌍 Support for cryptocurrency conversion  
- 🔐 API key management via environment variables  
- ☁️ Deploy on cloud (AWS, GCP, Render)  

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork this repo and submit a pull request.

---

## 📜 License

This project is licensed under the MIT License.
