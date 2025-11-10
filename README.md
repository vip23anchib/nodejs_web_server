# nodejs_web_server

A tiny Node.js/Express project that serves HTML pages, static assets, and shows basic routing + logging. Perfect for learning how requests flow through a server (middleware → routes → responses).

## ✨ Features

* HTTP server with Express
* Basic routes (home, sub-pages, 404)
* Serves static files (CSS, images, data)
* Simple request logging to files
* Friendly project structure for beginners

## 🗂️ Project Structure

```
.
├─ css/                 # static styles
├─ data/                # example data (json, txt)
├─ img/                 # images used by pages
├─ logs/
│  ├─ eventLog.txt      # request logs
│  └─ errLog.txt        # error logs
├─ views/               # HTML pages (served by routes)
│  ├─ 404.html
│  ├─ index.html
│  ├─ new-page.html
│  └─ subdir/
│     ├─ index.html
│     └─ test.html
├─ logEvents.js         # tiny logging helper
├─ server.js            # main server (routes + middleware)
├─ package.json
└─ .gitignore
```

## 🚀 Get Started

### Prerequisites

* **Node.js** v18+ recommended
* **npm** (comes with Node)

### Install

```bash
npm install
```

### Run

```bash
# if package.json has "start": "node server.js"
npm start

# or run directly
node server.js
```

By default the server listens on **[http://localhost:3000](http://localhost:3000)** (change the port in `server.js` if needed).

## 🌐 Routes (examples)

| Method | Path                | What it does                     |
| -----: | ------------------- | -------------------------------- |
|    GET | `/`                 | Home page (`views/index.html`)   |
|    GET | `/new-page`         | New page (`views/new-page.html`) |
|    GET | `/subdir/`          | Subdir index                     |
|    GET | `/subdir/test.html` | Subdir test page                 |
|      * | *(anything else)*   | 404 page (`views/404.html`)      |

> If your exact paths differ, tweak this table to match `server.js`.

## 📦 Static Files

* CSS served from `/css/...`
* Images from `/img/...`
* Example data in `/data/...`

(Express’s static middleware is used so files in these folders are accessible by URL.)

## 📝 Logging

Requests and errors are appended to:

* `logs/eventLog.txt`
* `logs/errLog.txt`

The logging helper lives in `logEvents.js`.

## 🧪 Quick Test (cURL)

```bash
curl -i http://localhost:3000/
curl -i http://localhost:3000/new-page
curl -i http://localhost:3000/does-not-exist   # should return 404 page
```

## 🔧 Scripts (optional)

If you like auto-reload during development, add this to `package.json`:

```json
"scripts": {
  "start": "node server.js",
  "dev": "nodemon server.js"
}
```

Then run:

```bash
npm run dev
```

## 🤝 Contributing

Issues and PRs are welcome—this repo is mainly for learning, so suggestions that make the code clearer are appreciated.

