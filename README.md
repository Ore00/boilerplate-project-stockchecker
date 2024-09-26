
# Stock Price Checker Project

This is the Stock Price Checker project, part of the freeCodeCamp Information Security certification. 
You can find the challenge details on the [freeCodeCamp website](https://freecodecamp.org/learn/information-security/information-security-projects/stock-price-checker).

## Project Overview

The Stock Price Checker allows users to retrieve real-time stock prices, view price comparison data between two stocks, and vote on whether they like specific stocks. The system ensures that users' voting preferences are secure and cannot be tampered with.

## Key Features

- Retrieve real-time stock prices for a single stock symbol.
- Compare stock prices for two stocks.
- Vote for whether a user likes a specific stock.
- Implement security headers using `helmet` to secure the app.
- API handles cross-origin requests using `CORS`.

## Technologies Used

- Node.js
- Express
- Helmet (for securing HTTP headers)
- Chai and Chai-HTTP (for assertions and HTTP requests testing)
- dotenv (for environment variable management)
- CORS (to handle cross-origin requests)

## Installation and Setup

To run this project locally, follow the steps below:

1. Clone this repository:
    ```
    git clone https://github.com/Ore00/stockchecker.git
    ```

2. Navigate to the project directory:
    ```
    cd stockchecker
    ```

3. Install the required dependencies:
    ```
    npm install
    ```

4. Create a `.env` file in the root directory and add the following environment variables:
    ```
    NODE_ENV=development
    STOCK_API_KEY=your_stock_api_key
    ```

5. Start the development server:
    ```
    npm start
    ```

6. Run the tests to ensure everything is set up correctly:
    ```
    npm test
    ```

## API Endpoints

The following endpoints are available for interacting with the Stock Price Checker API:

- **GET** `/api/stock-prices?stock={symbol}`: Retrieve real-time stock data for a given stock symbol.
    - Example: `/api/stock-prices?stock=GOOG`

- **GET** `/api/stock-prices?stock={symbol1}&stock={symbol2}`: Compare stock prices for two stocks.
    - Example: `/api/stock-prices?stock=GOOG&stock=MSFT`

- **POST** `/api/stock-prices?stock={symbol}&like=true`: Like a stock and track the number of likes securely.

## Example Usage

1. Retrieve stock price for a single stock:
    ```
    GET /api/stock-prices?stock=GOOG
    ```

    Response:
    ```json
    {
      "stock": "GOOG",
      "price": "2800.50",
      "likes": 5
    }
    ```

2. Compare prices of two stocks:
    ```
    GET /api/stock-prices?stock=GOOG&stock=MSFT
    ```

    Response:
    ```json
    [
      { "stock": "GOOG", "price": "2800.50", "likes": 5 },
      { "stock": "MSFT", "price": "299.20", "likes": 3 }
    ]
    ```

## License

This project is licensed under the [MIT License](https://opensource.org/license/mit).