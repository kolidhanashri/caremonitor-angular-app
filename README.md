
# caremonitor-angular-app
angular application for caremonitor test

## Overview

This is a simple Angular application built for the CareMonitor UI Developer Interview Challenge. It implements authentication, protected routing, dashboard, and a list page with API integration — all backed by a `json-server` mock API using a local `db.json` file.

---

## Features

### 1. **Login Page**
- Email and password fields.
- On submission, sends login request to `/api/login`.
- On success:
  - Stores token in cookies.
  - Redirects to the Dashboard.

``` 
Note - 
 For successful login use email and password as - 

 email - test@example.com
 password - password123

 this is stored in db.json file with login key.

 On login the login endpoint will fetch data from login array and match for valid record, and if found it will return the success reponse otherwise returns error for invalid credentials

 On login success it stores token value in cookie for authentication purpose.

```

### 2. **Authentication Handling**
- Uses cookies (`ngx-cookie-service`) to store the auth token.
- Protects `dashboard` and `list` routes using route guards.
- Logout clears cookie and redirects to login page.

### 3. **Dashboard Page**
- Displays welcome message with user's email.
- Navigation link to List Page.
- Logout button.

### 4. **List Page**
- Fetches items from `/api/items`.
- Uses **Component Store** or **Signal Store** for state management.
- Includes loading and error handling.

---

## Technologies Used

- **Angular 19+**
- **RxJS**
- **Angular Router**
- **Angular Component**
- **Angular Material** (optional, used for UI)
- **ngx-cookie-service**
- **json-server** (mock backend)


---

## Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/your-username/caremonitor-angular-challenge.git
cd caremonitor-angular-challenge 
```
### 2. Install Angular dependencies
 
```
npm install

```
### 3. Install and run json-server

```
npm install -g json-server
json-server --watch db.json --port 3000

Make sure db.json contains mock data for:

1. users with email, password, and token

2. items with id, name, and description

-- This will provide enpoint as - 
http://localhost:3000/login
http://localhost:3000/items

```

### 4. Run Angular app

```
ng serve

```
Open http://localhost:4200




