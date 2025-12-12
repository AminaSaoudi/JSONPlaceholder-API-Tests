# JSONPlaceholder API Contract Tests
[![API Contract Tests](https://github.com/AminaSaoudi/JSONPlaceholder-API-Tests/actions/workflows/postman-tests.yml/badge.svg)](https://github.com/AminaSaoudi/JSONPlaceholder-API-Tests/actions/workflows/postman-tests.yml)

This repository contains automated **API contract and health tests** for the public JSONPlaceholder API using Postman.  
The goal is to ensure response structure, data types, and status codes remain consistent with the documented API behavior.

---

##  Overview

This project validates:

- HTTP status codes  
- Response times  
- JSON schema/contract for posts  

Tests run automatically using:

- **Postman**
- **Newman**
- **GitHub Actions CI pipeline**

---

##  Project Structure

```
/postman/
  ├── JSONPlaceholder_API_Contract_Tests.postman_collection.json
  └── Development_Environment.json
.github/workflows/
  └── api-tests.yml
```

---

##  How to Run Locally

### 1. Install Newman

```bash
npm install -g newman
```

### 2. Run the Collection

```bash
newman run "postman/JSONPlaceholder_API_Contract_Tests.postman_collection.json" -e "postman/Development_Environment.json"
```

---

##  API Under Test

All tests run against:

```
https://jsonplaceholder.typicode.com
```

The base URL is configured via the `baseUrl` environment variable in the environment file.

## Continuous Integration (GitHub Actions)

This project includes a CI pipeline that automatically runs all API tests on:

Every push

Every pull request
