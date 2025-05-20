# 🍻 Online Digital Menu

A sleek, mobile-friendly beer menu built with Node.js, Express, and a JSON file as the database. Ideal for bars or small venues looking to showcase their selection with style — no external database or CMS required.

---

## ✨ Features

- 📦 **Node.js backend with Express**
- 🧾 JSON-based "database" (no SQL setup!)
- 🌐 REST API for menu retrieval
- 🎨 Stylish, responsive frontend (HTML/CSS/JS)
- 🏳️‍🌈 Country flags via flag-icons
- 🏅 Category emojis based on awards
- 🧪 Includes basic unit tests using supertest
- 🐳 Docker + Docker Compose ready

---

## 📁 Project Structure

```
online-menu/
├── public/              # Frontend files
│   ├── index.html       # Web UI
│   ├── script.js        # JS to fetch and display menu
│   ├── styles.css       # Custom styling
│   └── menu.json        # JSON "database"
├── index.js             # Express server
├── Dockerfile           # Docker image definition
├── docker-compose.yml   # Docker Compose config
├── package.json
├── README.md
└── __tests__/menu.test.js # Basic API test
```

---

## 🧾 JSON Menu Format

`public/menu.json`:

```json
{
    "categories": [
        {
            "name": "1 - Best Beers",
            "items": [
                {
                    "name": "Punk IPA",
                    "brand": "BrewDog",
                    "type": "IPA",
                    "country": "gb",
                    "abv": "5.6%"
                }
            ]
        }
    ]
}
```

Each item requires:

- `name`: Product name
- `brand`: Brewery or brand
- `type`: Used for coloring/type detection
- `country`: ISO 3166-1 alpha-2 country code (e.g., `fr`, `us`)
- `abv`: Alcohol content

---

## 🚀 Getting Started

### 🔧 Prerequisites

- Node.js (v18+)
- npm

### 🖥️ Local Development

```bash
git clone https://github.com/PERRETJonatan/OnlineMenu.git
cd OnlineMenu
npm install
npm start
```

Open your browser: [http://localhost:3000](http://localhost:3000)

### 🐳 Docker

Build & Run:

```bash
docker-compose up --build
```

App will be available at: [http://localhost:3000](http://localhost:3000)

---

## 🔌 API

**GET** `/api/menu`  
Returns the full menu JSON from `public/menu.json`.

**Example response:**

```json
{
    "categories": [
        {
            "name": "1 - Gold Winners",
            "items": [...]
        }
    ]
}
```

---

## 🧪 Testing

Basic test using supertest to ensure API is working:

```bash
npm install --save-dev supertest jest
npx jest
```

---

## 🖼️ Frontend UI

- Dynamically loads menu from the backend
- Category titles display emoji medals (🥇, 🥈, 🥉)
- Flags from flag-icons
- Type detection highlights the beer style (e.g., IPA, Blonde)

---

## 📦 Dependencies

- `express` – Web server
- `fs` – File system access for reading JSON
- `flag-icons` – For country flags
- `supertest` – API testing
- `jest` – Test runner

---

## 📝 License

MIT License
