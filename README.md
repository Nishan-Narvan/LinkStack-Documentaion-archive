# LinkStack 🔗-Documentaion-archive
"Note: The source code for this project was lost due to data corruption, but this repository serves as documentation of the implementation and functionality."


![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Tech](https://img.shields.io/badge/Stack-MERN-blue)

## Overview
LinkStack allows users to aggregate their links in one place.

##  Key Features

* ** Secure Authentication:** User signup and login using **JWT (JSON Web Tokens)** and bcrypt for password hashing.
* **Categorization:** Organize links by platform (YouTube Videos, X/Twitter Threads, Notion Pages, etc.).
* **Embeds:** Automatically detects link types and renders the appropriate preview card (e.g., YouTube Player or Tweet Card) instead of plain text.
* **Sharing Toggle:**
    * **ON:** Generates a shareable public link (e.g., `/user/nishan`). Anyone with the link can view the collection.
    * **OFF:** The public endpoint is disabled. Accessing the link returns a `OOPs, the sharing link has been disabled` .

---

## 🛠️Tech Stack

* **FE:** React.js, Tailwind CSS (for the dashboard and public view)
* **BE:** Node.js, Express.js
* **DB:** MongoDB (storing Users, Links, and Privacy Settings)
* **Auth:** JWT, Bcrypt.js

---


https://github.com/user-attachments/assets/10cacfa9-32d6-40a8-8899-caa834fe46ea


##  Backend Logic 


1.  **DB Schema:** The `User` model contains a flag.
2.  **API :** `GET /api/public/:username`
3.  **Middleware :**
    * The server checks if the user exists.
    * It checks the  flag.
    * **If `true`:** Returns the array of links and profile info.
    * **If `false`:** Immediately halts and returns `error`

