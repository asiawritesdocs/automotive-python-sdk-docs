# Automotive Python SDK: Quickstart Guide 🐍

This guide demonstrates how to integrate the Automotive Telematics API into your Python applications using our official SDK.

---

## 🔧 Installation

To get started, install the SDK using `pip`. 

```bash
pip install automotive-telematics-sdk
```

## 🚀 Getting Started

### Initialize the Client
To communicate with the API, you must first initialize the client with your secret API key.

```python
from automotive_sdk import VehicleClient

# Initialize with your API Key
client = VehicleClient(api_key="YOUR_SECRET_KEY")
```

Fetch a Service Record
Once initialized, you can retrieve specific service records with just a few lines of code.

```python
# Fetch record by ID

record = client.get_service_record(record_id="12345")

print(f"Service Date: {record.date}")
print(f"Type: {record.service_type}")
print(f"Mileage: {record.mileage}")
```

Replace a Service Record (`PUT`)
Replacing a record is handled through the `update_record` method.

```python
updated_data = {
    "date": "04-15-2026",
    "service_type": "Tire Rotation",
    "mileage": 185500
}

client.update_record(record_id="12345", data=updated_data)
print("Record successfully updated!")
```

🛡 Exception Handling
The SDK provides built-in exceptions to help you manage API errors gracefully.

|Exception|Cause|
|---|---|
|`AuthenticationError`|Invalid or missing API Key (401).|
|`ResourceNotFoundError`|The requested record ID does not exist (404).|
|`ValidationError`|Missing or invalid data fields (422).|

📂 About This Documentation

This project demonstrates the ability to document SDKs and library integrations. It showcases a working knowledge of Python syntax, package management, and developer-friendly error handling.
