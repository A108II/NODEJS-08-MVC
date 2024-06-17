# README

## Overview

This project is a simple Express.js application that serves as an API for managing employee records. The application includes routes for basic CRUD (Create, Read, Update, Delete) operations and error handling.

## Table of Contents

1. [Project Structure](#project-structure)
2. [Middleware](#middleware)
3. [Routes](#routes)
   - [Root Routes](#root-routes)
   - [Employee Routes](#employee-routes)
4. [Error Handling](#error-handling)
5. [Controllers](#controllers)
6. [Configuration](#configuration)
7. [Summary](#summary)

## Project Structure

The project has the following structure:
- `server.js`: Main entry point for the application.
- `routes/`: Directory containing route definitions.
  - `api/`: Subdirectory containing API route definitions.
    - `employee.js`: Routes for employee-related endpoints.
  - `root.js`: Routes for the root endpoints.
- `controllers/`: Directory containing controller logic for handling requests.
  - `emp_controller.js`: Contains the logic for managing employee data.
- `middleware/`: Directory containing middleware functions.
  - `log_events.js`: Middleware for logging events.
  - `error_handler.js`: Middleware for handling errors.
- `config/`: Directory containing configuration files.
  - `cors_options.js`: Configuration for Cross-Origin Resource Sharing (CORS).
- `model/`: Directory containing data models.
  - `employee.json`: JSON file containing employee data.
- `views/`: Directory containing HTML views.
  - `404.html`: Custom 404 error page.

## Middleware

- **Logger**: Logs requests and responses.
- **CORS**: Handles Cross-Origin Resource Sharing using the settings defined in `cors_options.js`.
- **Error Handler**: Catches and handles errors gracefully.

## Routes

### Root Routes

- **Static Files**: Serves static files from the `public` directory.
- **Root Route**: 
  - Handles requests to `/` and serves the `index.html` file.
  - File: `routes/root.js`

### Employee Routes

- **Get All Employees**: 
  - Method: `GET`
  - Path: `/employee`
  - Description: Retrieves a list of all employees.
- **Add Employee**: 
  - Method: `POST`
  - Path: `/employee`
  - Description: Adds a new employee to the list.
- **Update Employee**: 
  - Method: `PUT`
  - Path: `/employee`
  - Description: Updates an existing employee's information.
- **Delete Employee**: 
  - Method: `DELETE`
  - Path: `/employee`
  - Description: Deletes an employee by ID.
- **Get Employee by ID**: 
  - Method: `GET`
  - Path: `/employee/:id`
  - Description: Retrieves an employee by ID.

## Error Handling

- **404 Not Found**: 
  - Catches all undefined routes and returns a custom 404 page.
  - Supports HTML, JSON, and plain text responses based on the request headers.

## Controllers

- **emp_controller.js**: Contains functions to handle employee data operations:
  - `get_all_employees`: Returns a list of all employees.
  - `add_employee`: Adds a new employee.
  - `update_employee`: Updates an existing employee's details.
  - `delete_employee`: Deletes an employee.
  - `get_emp_id`: Retrieves an employee by ID.

## Configuration

- **CORS**: Configured to allow specific origins as defined in `config/cors_options.js`.

## Summary

This Express.js application provides a simple REST API for managing employee records with complete CRUD functionality, custom error handling, and logging. The project is structured to separate concerns, making it easy to manage and extend.