# JSONPlaceholder API Contract Tests

This repository contains automated **API contract and health tests** for the public JSONPlaceholder API using Postman.  
The goal is to ensure response structure, data types, and status codes remain consistent with the documented API behavior.

---

## 🚀 Overview

This project validates:

- HTTP status codes  
- Response times  
- JSON schema/contract for posts  
- Handling of path parameters  
- Stability of the `/posts` resources  

Tests run automatically using:

- **Postman**
- **Newman**
- **GitHub Actions CI pipeline**

---

## 📁 Project Structure

```
/postman/
  ├── JSONPlaceholder API Contract Tests.postman_collection.json
  └── Development Environment.json
.github/workflows/
  └── api-tests.yml
```

---

## 🧪 How to Run Locally

### 1. Install Newman

```bash
npm install -g newman
```

### 2. Run the Collection

```bash
newman run "postman/JSONPlaceholder API Contract Tests.postman_collection.json" \
  -e "postman/Development Environment.json"
```

### 3. Run with Allure Report (Optional)

```bash
npm install newman-reporter-allure allure-commandline

newman run "postman/JSONPlaceholder API Contract Tests.postman_collection.json" \
  -e "postman/Development Environment.json" \
  -r allure

allure generate allure-results --clean -o allure-report
allure open allure-report
```

---

## 🌐 API Under Test

All tests run against:

```
https://jsonplaceholder.typicode.com
```

The base URL is configured via the `baseUrl` environment variable in the environment file.
