# Data Generator

## Overview
The Data Generator is a Python-based tool designed to simulate financial data for testing and development purposes. It generates realistic stock market data, including stock prices, volume, and additional metadata such as order books, news sentiment, and economic indicators. The generated data is sent to a configured API endpoint.

---

## Features
1. **Stock Price Simulation**:
   - Generates stock prices (open, close, high, low) and volume.
2. **Additional Data Types**:
   - Order book data.
   - News sentiment analysis.
   - Market metrics.
   - Economic indicators.
3. **Multi-threading**:
   - Runs multiple data streams simultaneously.
4. **API Integration**:
   - Sends data to an API endpoint for ingestion.

---

## Files
### `generator.py`
- **Purpose**: Main script to generate and send data.
- **Key Functions**:
  - `generate_data()`: Generates stock price data.
  - `generate_additional_data()`: Creates additional financial data.
  - `send_data(data)`: Sends generated data to the API endpoint.
  - `send_additional_data()`: Handles continuous generation of additional data in a separate thread.

### `manager.sh`
- **Purpose**: Bash script to manage the lifecycle of the data generator.
- **Usage**:
  - Start, stop, or monitor the data generator process.

### `requirements.txt`
- **Purpose**: Lists the dependencies required to run the data generator.
- **Dependencies**:
  - `requests`
  - `numpy`
  - `psutil`

---

## Configuration
### API Endpoint
Set the API endpoint in `generator.py`:
```python
api_endpoint = "http://localhost:5000/ingest"
```
Update the URL to match the desired data ingestion service endpoint.

---

## Usage

### Requirements
- **Python 3.x**
- Install dependencies:
  ```bash
  pip install requests numpy psutil
  ```

### Running the Data Generator
1. **Direct Execution**:
   ```bash
   python generator.py
   ```
2. **Using `manager.sh`**:
   ```bash
   chmod +x manager.sh
   ./manager.sh init
   ./manager.sh start
   ```
   Stopping the Data Generator

    ```bash
    ./manager.sh stop
   ```
---

## Example Output
### Generated Stock Price Data
```json
{
    "stock_symbol": "AAPL",
    "opening_price": 1023.45,
    "closing_price": 1032.67,
    "high": 1045.89,
    "low": 1012.34,
    "volume": 5123,
    "timestamp": 1700000000.123456
}
```

### Additional Data (Order Book Example)
```json
{
    "data_type": "order_book",
    "timestamp": 1700000000.123456,
    "stock_symbol": "GOOGL",
    "order_type": "buy",
    "price": 1345.67,
    "quantity": 25
}
```

---

## Authors
- Mahdi Shekari Saryazdi (mahdiiiishekari@gmail.com)

