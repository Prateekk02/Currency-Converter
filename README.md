# Currency Converter App

## Overview
The **Currency Converter App** is a React-based web application that allows users to convert currency values between different currencies using real-time exchange rates. The app dynamically fetches data from an external API and provides an intuitive interface for currency conversion.

## Features
- Convert currency values between multiple currencies.
- Swap base and target currencies with a single button click.
- Real-time fetching of exchange rates based on the selected currency.
- Intuitive UI designed with Tailwind CSS.

## Technologies Used
- **React**: Core library for building user interfaces.
- **Vite**: Development server and build tool.
- **Tailwind CSS**: Utility-first CSS framework for styling.
- **JavaScript Fetch API**: For data fetching.

## Installation
Follow these steps to set up the project locally:

1. Clone the repository
2. Navigate to Project directory
```
 cd currency-converter
 ```  
 3. Install Dependencies
 ```
 npm install
 ```
 4. Start the development environment
 ```
 npm run dev 
 ``` 

## Usage
- Enter the amount in the From field.
- Select the base currency and target currency from the dropdown menus.
- Click the Convert button to see the converted amount.
- Use the Swap button to swap the base and target currencies.
## Components
1. useCurrencyInfo Hook
Fetches exchange rates based on the selected base currency using an API.

2. InputBox Component
Renders an input box for entering the amount and a dropdown for selecting a currency.

3. App Component
The main component managing the application’s state, currency conversion logic, and user interface.

## API Reference
- Endpoint: https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/[currency].json
- Method: GET
- Response: JSON object containing conversion rates for the specified base currency.
## Future Enhancements
- Add error handling for failed API requests.
- Implement caching mechanisms to reduce API calls.
- Add support for historical exchange rates.
## License
This project is licensed under the MIT License.
