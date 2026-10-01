# Master Test Plan - JSONPlaceholder Postman Automation

## 1. Test Plan Identifier
JP-POSTMAN-MTP-V1.0

## 2. Introduction & Purpose
This document descries the Test plan for JSONPlaceholder automation project. The goal is to test all key API functions of the posts module using Postman.

## 3. Test Items
The test item is the JSONPlaceholder REST API post module, available at: https://jsonplaceholder.typicode.com

## 4. Scope of Testing
### 4.1 Features in Scope
* GET all posts (successful list retrieval)
* GET existing post by ID (successful path)
* GET non-existing post by ID (negative path with out-of-range ID)
* GET post with invalid ID format (negative patch with non-numeric ID)
* POST a new post with valid data (successful path)
* POST a new post with empty data (negative path)
* PUT an existing post (successful full update)
* PATCH an existing post (successful partial update)
* DELETE an existing post (successful removal)

### 4.2 Out of Scope
* Performance and Load Testing of the API
* Security and Authorization Testing (OAuth/Tokens)
* Destructive data testing (SQL Injection / script injection via API)

## 5. Environmental Needs
* Operating System: Linux, Ubuntu 26.04
* Testing Frameworks and Tools: Postman Desktop App (v12)
* Version Control System: Git and GitHub

## 6. Entry & Exit Criteria
### 6.1 Entry Criteria
* Access to the Internet
* Stability and availability of the JSONPlaceholder API
* Postman Desktop App installed and connected to GitHub repository

### 6.2 Exit Criteria
* All 9 planned API test cases are executed in Postman
* 100% Pass Rate for successful paths
* Postman collection is successfully synchronized and pushed t the GitHub repository