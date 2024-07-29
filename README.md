# Finance Management API

## Overview

The Finance Management API is designed to help users manage their expenses effectively. This implementation leverages the repository pattern with MongoDB, providing a centralized hub for seamless interactions between the expense model and the controller functions.

## Objectives

1. **Repository Methods Implementation (`expense.repository.js`):**
   - `addExpense`: Insert a new expense into the database.
   - `getAllExpenses`: Retrieve all expenses from the database.
   - `getOne`: Fetch a single expense by its ID.
   - `filterExpenses`: Filter expenses based on criteria such as minimum amount, maximum amount, and recurring status.
   - `addTagToExpense`: Add a tag to an existing expense.

2. **Controller Refactoring:**
   - Integrate the new repository methods into the controller for various operations, ensuring a cohesive and efficient workflow.
   - Initialize the repository in the controller's constructor for efficient usage.
   - Bind the correct context (`this`) to the controller methods using arrow functions when defining routes.

## Getting Started

### Prerequisites

- Node.js
- MongoDB

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/finance-management-api.git
   ```
2. Navigate to the project directory:
   ```sh
   cd finance-management-api
   ```
3. Install the dependencies:
   ```sh
   npm install
   ```

### Configuration

1. Create a `.env` file in the root of the project.
2. Add the following environment variables to the `.env` file:
   ```env
   MONGODB_URI=your_mongodb_connection_string
   PORT=your_port_number
   ```

### Running the Application

1. Start the MongoDB server.
2. Run the application:
   ```sh
   npm start
   ```

## Usage

### Repository Methods

- **addExpense(expense)**: Insert a new expense into the database.
- **getAllExpenses()**: Retrieve all expenses from the database.
- **getOne(id)**: Fetch a single expense by its ID.
- **filterExpenses(criteria)**: Filter expenses based on criteria such as minimum amount, maximum amount, and recurring status.
- **addTagToExpense(id, tag)**: Add a tag to an existing expense.

### Example Requests

1. **Add Expense**
   ```sh
   POST /expenses
   {
     "description": "Lunch",
     "amount": 15.00,
     "date": "2024-07-29",
     "tags": ["food", "meal"]
   }
   ```

2. **Get All Expenses**
   ```sh
   GET /expenses
   ```

3. **Get One Expense**
   ```sh
   GET /expenses/:id
   ```

4. **Filter Expenses**
   ```sh
   GET /expenses/filter?minAmount=10&maxAmount=100&recurring=true
   ```

5. **Add Tag to Expense**
   ```sh
   POST /expenses/:id/tag
   {
     "tag": "work"
   }
   ```

## Contributing

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/yourFeature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/yourFeature`).
5. Open a pull request.
