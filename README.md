<h1 align="center">Hi, I'm Banti Kumar 👋</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1200&color=2F81F7&center=true&vCenter=true&width=520&lines=Web+Developer;Full-Stack+with+Node.js+and+Express;MongoDB+%26+MySQL;Based+in+Kolkata%2C+India" alt="Typing animation" />
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/ba-n-ti/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:bantikrsahuji123@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" /></a>
  <a href="https://x.com/Kumar24752Banti"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=bantikr-sahu2105&label=Profile+views&color=0e75b6&style=flat" alt="Profile views" />
</p>

<p align="center">
  <a href="#about-me">About</a> •
  <a href="#tech-stack">Tech Stack</a> •
  <a href="#featured-projects">Projects</a> •
  <a href="#github-stats">Stats</a> •
  <a href="#lets-connect">Contact</a>
</p>

## About Me

- 📍 Based in Kolkata, West Bengal, India
- 🌐 I build full-stack web apps with Node.js, Express.js and EJS
- 🗄️ I work with MongoDB and MySQL databases
- 🚀 My projects are deployed on Vercel
- 📫 Reach me at [bantikrsahuji123@gmail.com](mailto:bantikrsahuji123@gmail.com)

## Tech Stack

<p>
  <img src="https://skillicons.dev/icons?i=js,html,css,nodejs,express,mongodb,mysql,git,github,vercel" alt="Tech stack icons" />
</p>

JavaScript, HTML, CSS, Node.js, Express.js, EJS, MongoDB, MySQL, Git, GitHub, Vercel

## Featured Projects

Click a project to see more details.

<details>
<summary><b>🏡 Wanderlust</b>: Airbnb-inspired travel listings app</summary>

<br />

A full-stack web app for browsing and managing travel listings.

- Secure user authentication
- Create, read, update and delete (CRUD) operations for listings
- Responsive interface with dynamic server-side rendering
- Built with Express.js, EJS and MongoDB

<a href="https://wanderlust-dusky-iota.vercel.app/listings/"><img src="https://img.shields.io/badge/Live_Demo-Open-2ea44f?style=for-the-badge&logo=vercel&logoColor=white" alt="Live demo" /></a>
<a href="https://github.com/bantikr-sahu2105/Wanderlust"><img src="https://img.shields.io/badge/View_Code-181717?style=for-the-badge&logo=github&logoColor=white" alt="View code" /></a>

</details>

<details>
<summary><b>📈 TrackIn Trade</b>: trading journal platform</summary>

<br />

A platform that helps traders record, review and improve their trades.

- Secure sign up and login
- Add, edit and delete trade entries
- Insights to help traders study their own performance
- Built with Node.js, Express.js, EJS and MySQL

<a href="https://track-in-final.vercel.app/home"><img src="https://img.shields.io/badge/Live_Demo-Open-2ea44f?style=for-the-badge&logo=vercel&logoColor=white" alt="Live demo" /></a>
<a href="https://github.com/bantikr-sahu2105/TrackIn-Trade"><img src="https://img.shields.io/badge/View_Code-181717?style=for-the-badge&logo=github&logoColor=white" alt="View code" /></a>

</details>

<details>
<summary><b>🧠 Project Chronos (chronos_agents)</b>: distributed stock market simulation</summary>

<br />

Project Chronos is a simulated stock market made of many separate programs that talk to each other. Instead of testing a trading idea on old price data, it creates a live market where AI traders and rule-based traders buy and sell against each other in real time.

This is my fork of [aetherstackofficial/chronos_agents](https://github.com/aetherstackofficial/chronos_agents).

**Main parts**

- **Matching engine (server):** keeps a Level 2 order book, which is the list of buy and sell orders at every price. It matches orders by price priority, handles partial fills, and shares market data as JSON, such as VWAP, 14-period RSI, volatility and order flow imbalance.
- **Agent swarm (clients):** around 100 trading agents run at the same time and talk to the engine over ZeroMQ.
- **AI brains:** reinforcement learning models trained with PPO using PyTorch and Stable-Baselines3. They act as market makers and large institutional traders.
- **Macro oracle:** uses the Google Gemini API to read simulated breaking news and give it a sentiment score between minus 1 and plus 1. Strong news creates sudden market shocks.

**Types of traders**

- **Market makers (15 agents):** start with $1M to $5M. They keep adjusting the gap between their buy and sell prices based on inventory risk and order flow toxicity.
- **Institutional whales (4 agents):** start with $5M to $20M. They are trained to follow big trends and place large block trades, with a deadzone rule so they do not waste money on too many small trades.
- **Retail swarm (80 agents):** start with $10k to $100k. They follow simple RSI crossover rules to copy emotional retail trading. A liquidation engine removes bankrupt agents and adds new ones, so the market never goes quiet.

**Design choices that make it work**

- **Pull-based notice board:** agents ask the engine for data using request and reply, instead of the engine broadcasting to everyone. This reduces network and CPU load.
- **Deadlock protection:** the engine uses a ZeroMQ poller with 50 ms timeouts, so one crashed agent cannot freeze the whole system.
- **Realistic activity:** agents sleep and wake at random. In quiet periods only about 30% are active, and big news wakes all of them. Small random noise is added to order flow to copy real exchange behaviour.
- **Shared brain pattern:** agents of the same type share one model in memory to save RAM.
- **Fallback for API limits:** if the Gemini API hits its limit, a local fallback keeps the news shocks running.
- **Speed:** the project README reports more than 1,200 neural network passes per second on a local machine.

**Tech stack:** Python 3.11+, asyncio, ZeroMQ (pyzmq), PyTorch, Stable-Baselines3 (PPO), Gymnasium, Google GenAI SDK, Pandas, NumPy

**How to run:** open three terminals inside the `swarm_orchestrator` folder and start the engine with `python true_engine.py`, then the agents with `python main.py`, then the oracle with `python oracle.py`. A `.env` file with `ZMQ_HOST`, `ZMQ_ORDER_PORT` and `GEMINI_API_KEY` is needed.

<a href="https://github.com/bantikr-sahu2105/chronos_agents"><img src="https://img.shields.io/badge/View_Code-181717?style=for-the-badge&logo=github&logoColor=white" alt="View code" /></a>
<a href="https://github.com/aetherstackofficial/chronos_agents"><img src="https://img.shields.io/badge/Original_Repo-0A66C2?style=for-the-badge&logo=github&logoColor=white" alt="Original repo" /></a>

</details>

<details>
<summary><b>📂 Other repositories</b></summary>

<br />

- [aeera-hackathon](https://github.com/bantikr-sahu2105/aeera-hackathon): fork of a hackathon project
- [Demo-Delta](https://github.com/bantikr-sahu2105/Demo-Delta): demo repository for Git and GitHub

</details>

## GitHub Stats

<p align="center">
  <img src="https://img.shields.io/github/followers/bantikr-sahu2105?style=for-the-badge&logo=github&label=Followers" alt="Followers" />
  <img src="https://img.shields.io/github/stars/bantikr-sahu2105/TrackIn-Trade?style=for-the-badge&logo=github&label=TrackIn+Trade+stars" alt="TrackIn Trade stars" />
  <img src="https://img.shields.io/github/stars/bantikr-sahu2105/Wanderlust?style=for-the-badge&logo=github&label=Wanderlust+stars" alt="Wanderlust stars" />
</p>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/bantikr-sahu2105/TrackIn-Trade?style=for-the-badge&label=TrackIn+Trade+last+commit" alt="TrackIn Trade last commit" />
  <img src="https://img.shields.io/github/last-commit/bantikr-sahu2105/Wanderlust?style=for-the-badge&label=Wanderlust+last+commit" alt="Wanderlust last commit" />
</p>

## Let's Connect

I am open to web development opportunities and collaboration. Pick any option below.

<p>
  <a href="https://www.linkedin.com/in/ba-n-ti/"><img src="https://img.shields.io/badge/Message_me_on-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:bantikrsahuji123@gmail.com"><img src="https://img.shields.io/badge/Email_me_at-Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" /></a>
  <a href="https://x.com/Kumar24752Banti"><img src="https://img.shields.io/badge/Follow_me_on-X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
</p>
