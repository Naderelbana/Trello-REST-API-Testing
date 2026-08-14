# Trello REST API Testing Project

A manual API testing project for the Trello REST API using Postman.  
The project focuses on functional API testing, positive and negative scenarios, CRUD operations, request chaining, response assertions, and relationship/data integrity validation between Boards, Lists, and Cards.

## Project Overview

The goal of this project is to validate the main Trello API workflows and make sure resources are created, retrieved, updated, and deleted correctly while maintaining the expected relationships between Boards, Lists, and Cards.

## Tools & Technologies

- Postman
- Trello REST API
- JavaScript (Postman test scripts)
- Postman Collection Runner
- Environment Variables

## Authentication

The project uses Trello API authentication with:

- API Key
- API Token

Sensitive credentials are stored as environment variables and must not be committed to the repository.

## Scope

### Authentication
- Verify authenticated user

### Boards
- Create Board
- Get Board
- Get Board with non-existent ID
- Update Board
- Delete Board
- Verify Board deletion

### Lists
- Create List
- Get List
- Get List with non-existent ID
- Update List name
- Verify List update
- Archive List
- Verify List archive
- Unarchive List

### Cards
- Create Card
- Get Card
- Get Card with non-existent ID
- Update Card name
- Verify Card update
- Delete Card
- Verify Card deletion

### Negative Testing
- Create Card without required `idList`
- Create List without required `name`
- Update Card with non-existent ID

### Relationship / Data Integrity Testing
- Get Cards on a Board
- Get Lists on a Board
- Get the Board a List is on
- Get Cards in a List
- Get the Board a Card is on
- Get the List of a Card

## Testing Techniques

- Positive Testing
- Negative Testing
- CRUD Testing
- API Contract / Documentation-based Testing
- Status Code Validation
- Response Body Validation
- Request Chaining
- Environment Variables
- Resource Relationship Validation
- Data Integrity Testing
- Post-condition Verification

## Request Chaining

The project dynamically extracts resource IDs from API responses and stores them in Postman environment variables.

Example flow:

Board → List → Card

These IDs are then reused in subsequent requests to validate relationships between resources.

## Assertions

Postman `pm.test()` assertions are used to validate:

- HTTP status codes
- Response structure
- Required fields
- Resource IDs
- Resource names
- Board/List/Card relationships
- Error responses for negative scenarios

## Test Execution

The complete Postman Collection was executed using the Postman Collection Runner.

### Latest Execution Result

| Metric | Result |
|---|---:|
| Requests / Test Cases | 33 |
| Assertions | 97 |
| Passed Assertions | 97 |
| Failed Assertions | 0 |
| Errors | 0 |
| Skipped | 0 |
| Iterations | 1 |

**Execution Result: 97/97 assertions passed successfully.**

## Project Structure

```text
Trello-API-Testing/
│
├── README.md
├── Trello_API_Testing.postman_collection.json
└── Trello_Testing_Environment.json
```

> The environment file must contain no real API Token or other sensitive credentials before being uploaded to GitHub.

## How to Run

1. Import the Postman Collection.
2. Import the Postman Environment.
3. Add your own Trello API Key and API Token to the environment.
4. Select the environment in Postman.
5. Run the collection using Postman Collection Runner.
6. Review the assertion results.

## Notes

- Expected results were defined using the Trello REST API documentation.
- Assertions were written to validate the documented behavior and the resource relationships required by each endpoint.
- No real credentials should be stored in the GitHub repository.

## Author

## Author

Nader Elbanna  
Junior QA Engineer | Manual Testing | API Testing