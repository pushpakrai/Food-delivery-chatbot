# Food Delivery Chatbot Using Dialogflow and FastAPI.

## Overview
This project demonstrates an end-to-end implementation of a food delivery chatbot using Dialogflow, Python (FastAPI), and MySQL. It includes natural language processing (NLP) concepts like intents, entities, and contexts to create a conversational interface. The chatbot interacts with a backend server to handle real-time orders and integrates with a database for order management.

---

## Directory Structure

```
backend/
    Contains Python FastAPI backend code

db/
    Includes the MySQL database dump. Import this using MySQL Workbench or other tools.

dialogflow_assets/
    Contains training phrases, intents, and entities for Dialogflow setup.

frontend/
    Holds the website code for user interaction.
```

---

## Setup Instructions

### 1. Install Required Modules

To set up the backend, install the necessary dependencies:

```bash
pip install mysql-connector
pip install "fastapi[all]"
```

Alternatively, you can install all dependencies at once using the `requirements.txt` file located in the `backend` directory:

```bash
pip install -r backend/requirements.txt
```

### 2. Start FastAPI Backend Server

To run the backend server:

1. Navigate to the `backend` directory:

```bash
cd backend
```

2. Start the FastAPI server with the following command:

```bash
uvicorn main:app --reload
```

The server will now be available at `http://127.0.0.1:8000`.

### 3. MySQL Database Setup

Import the provided MySQL database dump into your MySQL server using MySQL Workbench:

1. Open MySQL Workbench and connect to your database server.
2. Go to the "Server" menu and select "Data Import".
3. Choose the provided `.sql` dump file and import it into your database.

### 4. Ngrok Setup for HTTPS Tunneling

To allow external services like Dialogflow to securely communicate with your local FastAPI server, use ngrok:

1. Download and install ngrok from [here](https://ngrok.com/download).
2. Extract the ZIP file and place `ngrok.exe` in a folder.
3. Open a command prompt in the folder and run the following command:

```bash
ngrok http 8000
```

This will provide an HTTPS URL (e.g., `https://abcd1234.ngrok.io`) that you can use to set up webhook endpoints in Dialogflow.

**Note:** Ngrok sessions may expire. If you encounter a "session expired" message, simply restart the ngrok process.

---

## Dialogflow Integration

### Dialogflow Assets

The `dialogflow_assets/` directory contains all the necessary training phrases, intents, entities, and context configurations required for the chatbot. Import these assets into your Dialogflow project for the chatbot to function properly.

---

## Key Features

- **Intents and Entities**: The chatbot understands various intents (e.g., placing an order, tracking orders) and extracts relevant entities like food item names and quantities.
- **Order Management**: Integration with MySQL to store and retrieve order information.
- **Real-Time Updates**: Provides real-time updates about order status, allowing users to track their deliveries.
- **Webhook Fulfillment**: The FastAPI server handles fulfillment requests from Dialogflow, allowing dynamic responses based on database interactions.

---

## Technologies Used

- **Dialogflow**: NLP platform for building conversational interfaces.
- **FastAPI**: Python web framework for building the backend.
- **MySQL**: Relational database to store order data.
- **ngrok**: Tool for exposing local servers to the internet via HTTPS.
- **HTML/CSS/JS**: Frontend technologies for building the user interface.

---

## Future Improvements

- **Voice Integration**: Add voice recognition to make the chatbot more interactive.
- **Payment Gateway**: Integrate a payment system to process food orders.
- **Mobile App**: Develop a mobile app to provide better accessibility.
