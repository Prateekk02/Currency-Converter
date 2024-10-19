# Currency Converter Application

## Overview
The **Currency Converter** application is built using **React** and allows users to convert currency values between different currencies using real-time data fetched from an external API. The application comprises several components and a custom hook to manage data fetching and rendering.

## Components

### 1. `useCurrencyInfo.js` Hook
This hook fetches currency information based on the selected base currency. It uses the `useState` and `useEffect` hooks to manage state and side effects.

- **State:**
  - `data`: Holds the fetched currency conversion rates for the selected base currency.

- **Logic:**
  - Takes `currency` as a parameter, representing the base currency (e.g., `"usd"`).
  - Builds the API URL dynamically using the selected base currency.
  - The `useEffect` hook fetches the currency data when the base currency changes. The data is then stored in the `data` state.

- **Return:**
  - Returns the `data` object containing the conversion rates for all supported currencies.

### 2. `InputBox.jsx` Component
This component is a reusable input box for the user to enter the amount and select a currency. It is used twice in the application: once for the base currency and once for the target currency.

- **Props:**
  - `label`: Label for the input box (e.g., `"From"`, `"To"`).
  - `amount`: Value for the amount input field.
  - `onAmountChange`: Function to update the amount state when the input value changes.
  - `onCurrencyChange`: Function to update the selected currency when the dropdown value changes.
  - `currencyOptions`: Array of currency options to be shown in the select dropdown.
  - `selectCurrency`: The currently selected currency.
  - `amountDisable` & `currencyDisable`: Flags to disable the amount input or currency dropdown if needed.
  - `className`: Additional CSS classes for styling.

- **Structure:**
  - Contains an input field for the amount and a dropdown for selecting the currency type.
  - Uses the `useId` hook to generate unique IDs for the input fields.

### 3. `App.jsx` Component
This is the main component that manages the state and logic for the entire application.

- **State:**
  - `amount`: Holds the value of the base currency amount entered by the user.
  - `from`: The base currency type selected (e.g., `"usd"`).
  - `to`: The target currency type selected (e.g., `"inr"`).
  - `convertedAmount`: Holds the converted amount based on the selected target currency.

- **Logic:**
  - `currencyInfo`: Fetches the conversion rates using the `useCurrencyInfo` hook based on the `from` currency.
  - `options`: An array of currency options derived from the keys of `currencyInfo`.
  - `swap`: A function to swap the base and target currencies and their respective amounts.
  - `convert`: A function to calculate and update the converted amount based on the selected target currency and current amount.

- **UI Layout:**
  - The layout contains a form with two `InputBox` components for the base and target currencies.
  - A button for swapping currencies and another button for submitting the form to trigger the conversion.

## Styling
- **Tailwind CSS**: Used for styling the components.
- The background image is fetched from a URL and applied as a cover image for the entire screen.

## Dependencies
- **React**: Core library for building the user interface.
- **Tailwind CSS**: Utility-first CSS framework for styling.
- **useId**: React hook for generating unique IDs.

## API Details
The currency data is fetched from the following API:

https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/[currency].json

This API returns the conversion rates for the base currency specified in the URL.