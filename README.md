# BTK Domain Block Checker

A lightweight, concurrent web tool designed to check if specific domains or URLs are blocked by the BTK authority. It handles high-volume bulk checks quickly by leveraging asynchronous worker pools directly in the browser.

## 🚀 Live Demo

You can access and use the live tool directly via GitHub Pages:
👉 **[INSERT YOUR GITHUB PAGES URL HERE]**
*(Example: `https://your-username.github.io/your-repo-name/`)*

---

## ✨ Features

* **Bulk Processing:** Paste multiple URLs or domains (one per line) to check them all at once.
* **High Performance:** Uses an asynchronous worker pool running up to **10 concurrent requests** simultaneously.
* **Smart Domain Normalization:** Automatically extracts and strips protocols (`https://`), paths, `www.` prefixes, and handles complex public suffixes (like `.com.tr`, `.net.tr`, etc.) before querying.
* **Live Metrics:** Real-time counters tracking *Total*, *Blocked*, *Not Blocked*, and *Error* counts as the queue processes.
* **Health Checks:** Automatically tests API connectivity before launching a bulk check to prevent wasted requests.

---

## 🛠️ How It Works

1.  **Input:** Paste your list of target domains/URLs into the textarea.
2.  **Normalization:** The script parses the raw strings into clean, top-level/secondary-level domains.
3.  **Authentication & API:** The app communicates with a backend checker API using a built-in secure token (`X-Auth-Token`).
4.  **Results:** Outputs a clean, real-time table dynamically color-coded by status (🔴 Blocked, 🟢 Not Blocked, 🟡 Error).

---

## ⚠️ Connectivity & CORS Note

Because this frontend application interacts with a remote API endpoint over HTTP (`http://31.210.43.134`), please keep the following in mind:

* **Office/VPN Networks:** Some corporate firewalls or strict VPN configurations might block direct connections to raw IP endpoints.
* **CORS Policy:** Ensure that the destination backend server allows Cross-Origin Resource Sharing (CORS) requests coming from your GitHub Pages domain. If you see persistent network errors, check your browser's developer console (F12).