# Multi-Database Analytics Dashboard

A full-stack application that demonstrates integration with MongoDB Atlas and Azure PostgreSQL, hosted on Azure services.

## Architecture

- Frontend: React (Azure Static Web Apps)
- Backend: Node.js/Express (Azure App Service)
- Databases: 
  - MongoDB Atlas (deployed on Azure)
  - Azure Database for PostgreSQL
- Analytics: Azure Functions

## Prerequisites

- Node.js (v14 or higher)
- Azure account
- MongoDB Atlas account
- Azure PostgreSQL database

## Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   npm run install:all
   ```

3. Create a `.env` file in the root directory with the following variables:
   ```
   # MongoDB Atlas Connection
   MONGODB_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<database>?retryWrites=true&w=majority

   # Azure PostgreSQL Connection
   POSTGRESQL_URI=postgresql://<username>:<password>@<server>.postgres.database.azure.com:5432/<database>?sslmode=require

   # Server Configuration
   PORT=3001
   NODE_ENV=development
   ```

4. Start the development servers:
   ```bash
   npm start
   ```

## Deployment to Azure

1. Frontend (React):
   - Deploy to Azure Static Web Apps
   - Configure build settings for React

2. Backend (Node.js/Express):
   - Deploy to Azure App Service
   - Configure environment variables
   - Set up continuous deployment

3. Azure Functions:
   - Deploy the functions directory to Azure Functions
   - Configure the timer trigger
   - Set up environment variables

## Features

- Real-time data display from both MongoDB and PostgreSQL
- Automated analytics processing via Azure Functions
- Modern UI with Material-UI components
- Secure database connections
- Error handling and loading states

## Development

- Frontend runs on port 3000
- Backend runs on port 3001
- Azure Functions can be tested locally using Azure Functions Core Tools

## Security Notes

- Never commit .env files
- Use Azure Key Vault for production secrets
- Enable SSL/TLS for all connections
- Implement proper authentication for production use 