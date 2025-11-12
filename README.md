# Practical 13 – Node.js Streaming & Content Negotiation  
**Submitted by:** Akshat Singh  
**Roll No:** GF202344124  
**Course / Program:** BCA FULL STACK DEVELOPER  
  

---

##  Overview
This project demonstrates two Node.js concepts:
1. **Streaming with client-abort awareness**
2. **Content negotiation (JSON vs XML)**

Both are implemented using **Express.js** and tested using a simple Node client that prints results directly in the terminal.

---

##  Setup Instructions

### Step 1: Install dependencies
```bash
npm init -y
npm install express
```

### Step 2: Run the server
```bash
node server.js
```
You should see:
```
Server listening at http://localhost:3000
Endpoints:
  /stream  -> streaming plain-text lines
  /data    -> JSON (default) or XML if ?format=xml
```

### Step 3: Run the combined client
Open a new terminal (keep the server running) and run:
```bash
node client.js
```

---

##  Output Explanation

### Task 1 — Streaming
The client connects to `/stream` and prints streaming lines like:
```
--- Connected to /stream — live lines below ---
STREAM 1 | 2025-11-12T09:00:01Z
STREAM 2 | 2025-11-12T09:00:02Z
...
--- /stream ended by server ---
```

### Task 2 — Content Negotiation
The client requests `/data` twice:

1. **Default (JSON)** — server responds with JSON containing message, author and time.
2. **XML** — client requests `/data?format=xml` and server responds with the same data in XML format.

---

##  Concepts Demonstrated
- Streaming using `res.write()`  
- Detecting client disconnect with `req.on('close')`  
- Backpressure handling via `'drain'` (where applicable)  
- Simple content negotiation (JSON ↔ XML)

---

##  Credentials
**Student Name:** Akshat Singh  
**Roll No:** GF202344124  
**Program:** BCA FULL STACK DEVELOPER  
 

