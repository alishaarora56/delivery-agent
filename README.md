# Delivery Agent

**Delivery Agent** is an autonomous browser-controlling AI that can navigate food delivery platforms (like UberEats or SkipTheDishes) and place orders for any food item, guided by natural-language objectives.

It uses **Playwright** for browser automation and **Anthropic’s Claude model** for decision-making, allowing it to interpret the web interface and issue actions such as clicking, scrolling, and typing, just like a human user.

---

## 🚀 Features

- Works with **any food or restaurant** 
- Uses **Playwright** for dynamic browser interaction
- Supports **preloaded cookies** for authentication and location persistence
- Generalized **prompt logic** that adapts to UberEats, SkipTheDishes, or other sites
- Can issue and execute commands: `CLICK`, `SCROLL`, `TYPE`, `ADD TO ORDER`, etc.

---

## 🧠 How It Works

1. The script loads saved cookies (`cookies.json`) to skip login and geolocation steps.  
2. It launches a Chromium browser via Playwright.  
3. Claude (via the Anthropic API) receives a simplified snapshot of the webpage and your goal (e.g., “Order sushi rolls”).  
4. The model returns a browser command like `CLICK 12` or `TYPESUBMIT 5 "sushi near me"`.  
5. The agent executes that command, repeating until the goal is met.

---

## ⚙️ Setup

### Requirements
- Python 3.9+
- [Playwright](https://playwright.dev/python/docs/intro)
- Anthropic API key (`export API_KEY=your_key_here`)
- Dependencies:
  ```bash
  pip install playwright anthropic selenium
  playwright install

