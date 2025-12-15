# Illuminati-Terminal-v10.0---The-Oracle-Build-Edition

👁️ Illuminati Terminal
The "Hedge Fund in a Box" – An Autonomous AI Market Intelligence System.

Illuminati Terminal is an advanced Python-based market scanner that automates the entire workflow of a quantitative analyst. It aggregates unstructured data (News/RSS), processes it with Natural Language Processing (NLP), maps it to financial assets, performs deep fundamental and technical analysis, and uses Generative AI (Google Gemini) to produce professional investment memos.

🚀 Key Features
1. 🧠 AI-Powered "Trend Hunter" Engine
Instead of just reading stock prices, the terminal "reads" the news to predict the future.

Semantic Scanning: It scans thousands of headlines from Economic Times, Reuters, Bloomberg, and Livemint.

Hype Scoring: It detects emerging themes like "Green Hydrogen", "Defense", or "Semiconductors" by analyzing keyword density and sentiment momentum.

Output: It generates a "Future Booming Industries" table, telling you where the money is flowing before the price moves.

2. 🛡️ Self-Healing Architecture
Designed to run on any machine (Local PC, Google Colab, Cloud Server) without breaking.

Auto-Installer: Automatically detects missing libraries (nselib, trafilatura, yfinance) and installs them on the fly.

API Resilience: If the Gemini AI model fails (e.g., gemini-1.5-flash 404 error), it automatically retries with gemini-pro or gemini-1.0 until it works.

Database Hygiene: Automatically cleans old SQLite schemas to prevent data corruption errors.

3. 🌊 Waterfall Data Engine
Ensures you never get "No Data" errors. The system fetches price data using a sophisticated fallback mechanism:

TwelveData (Primary): Professional-grade real-time data (if API key provided).

AlphaVantage (Secondary): Backup source for adjusted close prices.

Yahoo Finance (Tertiary): Reliable fallback for historical data and fundamentals.

4. 📊 "Omniscient" Analysis Lab
The core engine that crunches the numbers. It combines three distinct disciplines into one "Illuminati Score":

Deep Technicals: Calculates RSI, MACD (Moving Average Convergence Divergence), Bollinger Bands, and identifying Uptrend/Downtrend structures.

Deep Fundamentals: Performs a Discounted Cash Flow (DCF) valuation to find the Intrinsic Value of a stock. If cash flow data is missing, it intelligently falls back to a PE-based valuation model.

Risk Metrics: Calculates the Sharpe Ratio (Reward vs. Risk), Sortino Ratio, and Max Drawdown to punish volatile stocks.

5. ⚖️ "Bearish Logic" & Strategic Verdict
Most algo-traders are too optimistic. Illuminati v14.0 is a realist.

Punitive Scoring: It doesn't just award points for good traits; it subtracts points for red flags (e.g., -20 for Downtrend, -15 for Overbought RSI).

Clear Signals: It sorts stocks into Top Buys (Opportunities) and Top Sells (Warnings) tables so you know what to avoid.

Target Prices: It calculates precise price targets and time horizons (e.g., "Mid Term (3-6 Mos)") based on the volatility and valuation gap.

6. 📝 Executive Reporting Suite
It generates institutional-quality reports automatically.

Interactive HTML Dashboard: A searchable, filterable web report containing all news, trends, and strategy tables.

Excel Strategy Sheet: A raw data file for further analysis.

Deep Dive Text File: A transparent "math receipt" showing exactly how the target price and score for every single stock was calculated.

Auto-Emailer: Sends the entire briefing package to your inbox automatically after every run (requires Gmail App Password).

⚙️ How It Works in Real Life (The Workflow)
Imagine you set this script to run at 08:00 AM every morning. Here is the autonomous sequence it follows:

Wake Up & Self-Check: The script starts, checks if it has all the necessary Python libraries (pandas, ta, transformers), and installs any that are missing.

The "Wide Net" Cast: It connects to 8+ global RSS feeds and scrapes Google News for "Indian Stock Market" keywords. It reads the last 7 days of news to ensure relevance.

Entity Resolution: It reads the headlines (e.g., "Tata Motors plans new EV plant"). The MasterMapper engine recognizes "Tata Motors" and maps it to the ticker TATAMOTORS.NS using the full NSE database.

The Analysis Crunch:

It pulls the last 1 year of price data for TATAMOTORS.

Technicals: It sees the stock is above its 200-day moving average (+20 Points).

Fundamentals: It sees the stock is trading at ₹900 but the DCF Fair Value is ₹1,100 (+20 Points).

Verdict: It assigns a score of 80/100 and a label of "STRONG BUY".

The "AI Analyst" (Gemini): The system sends this data to Google's Gemini AI. The AI writes a human-readable summary: "Tata Motors shows strong momentum driven by EV expansion news. Technicals confirm a breakout..."

Dispatch: It packages the results into an HTML dashboard and an Excel sheet, attaches them to an email, and sends it to you.

Result: You wake up, check your phone, and have a complete hedge fund briefing before the market opens.

🛠️ Setup Guide
1. Prerequisites
You need a Google account (for Colab) or a Python environment (VS Code/PyCharm).

2. API Keys (Optional but Recommended)
For the full experience, get these free keys:

Gemini API Key: Get it here (For AI Summaries).

TwelveData Key: Get it here (For faster data).

3. Running in Google Colab (Easiest)
Open the script in Google Colab.

Press Play.

The script will detect it's in Colab and prompt you to enter your keys interactively.

Sit back and watch the "Illuminati" scan the market.

4. Running Locally (VS Code / Terminal)
Install the dependencies once (the script will try to do this for you, but good practice):

Bash

pip install yfinance pandas numpy requests feedparser tabulate reportlab nltk transformers schedule google-generativeai aiohttp xlsxwriter trafilatura rapidfuzz beautifulsoup4 ta jinja2 textblob nest_asyncio
Run the script:

Bash

python illuminati_terminal.py
Interactive Mode: python illuminati_terminal.py --interactive

Scheduler Mode: python illuminati_terminal.py --schedule (Runs daily at 08:00 AM).
