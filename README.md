# CricNews 🏏

> 🔥 This is a fun, research project developed with the intention to demonstrate [FireCrawl](https://www.firecrawl.dev/). 🔥

Welcome to **CricNews**! A TypeScript-powered Node.js library and Express API service for all things cricket news. Whether you're building a cricket app, a chatbot, or just want to keep up with the latest in the cricketing world, CricNews has got you covered. Let's dive in! 🚀

---

## Features ✨

- **Latest Cricket News** 🔖: Fetch real-time cricket updates from top sources.
- **Open Source & Self-Hosted** 🔗: Full permission to use this code in your projects (with proper licensing) and host the API on your infrastructure.
- **TypeScript Ready** 🛠️: Fully typed for a delightful developer experience.
- **FireCrawl Integration**: 🔥 Integrated with FireCrawl to support lightning-fast retrievals from news sources.

---

## Installation ⚙️

Getting started is simple! First, install CricNews using npm:

```bash
npm install cricnews
```

Or with Yarn:

```bash
yarn add cricnews
```

---

## Usage 🚀

Here’s a quick guide to getting CricNews up and running in your Node.js application.

### 1. Import the Library

```typescript
import CricNews from 'cricnews';

const cricNews = new CricNews({
  verbose: true, 
  fireCrawlApiKey: process.env.FIRECRAWL_API_KEY,
});
```

If you don't pass the FireCrawl API key, it will automatically pick the `FIRECRAWL_API_KEY` from your `.env` file.

### 2. Fetch News

```typescript
const latestNews = await cricNews.getLatestNews();
console.log(latestNews);
```

---

## API Endpoints 🌐

The built-in Express API allows you to serve cricket news effortlessly. Here's how to set it up:

### 1. Initialize the API

Your `index.js` file should look like this:

```typescript
import CricNewsAPI from 'cricnews/api';

const app = CricNewsAPI({
  apiKey: 'YOUR_API_KEY', // Replace with your API key
});

const port = 3000; 

const onStartCallback = () => {
  console.log('CricNews API is running on http://localhost:' + port);
};

app.start(port, onStartCallback);
```

Alternatively, to start the server, you could also use `npx`:

```bash
npx cricnews start-server --port 3000
```

This will start the server on port 3000.

### 2. Available Endpoints

| Endpoint               | Method | Description                    |
|------------------------|--------|--------------------------------|
| `/api/news/latest`     | GET    | Fetch the latest cricket news  |

---

## Environment Variables 📋

To configure CricNews, set up the following environment variables in your `.env` file:

```env
FIRECRAWL_API_KEY=firecrawl-api-key
PORT=3000 # Defaults to 3000 if not specified
```

---

## Example Project 🛠️

Check out the `/examples` folder for a complete example project showcasing CricNews in action. Simply clone the repository and run:

```bash
npm run start
```

---

## Contributing 🤝

We’d love your help to make CricNews even better! Here’s how you can contribute:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature-name`.
3. Make your changes and commit: `git commit -m 'Add your feature'`.
4. Push to the branch: `git push origin feature/your-feature-name`.
5. Open a pull request. 🎉

---

## License 📜

CricNews is open source and available under the [MIT License](LICENSE).

---

## Support ❤️

Need help? Have questions? Feel free to reach out by opening an issue or joining our community discussions. Let's make CricNews the go-to cricket library together!

---

Happy coding! 🏏
