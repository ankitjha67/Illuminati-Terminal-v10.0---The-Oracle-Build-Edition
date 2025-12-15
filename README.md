# Illuminati-Terminal-v10.0---The-Oracle-Build-Edition

👁️ Illuminati Terminal
The "Hedge Fund in a Box" – Autonomous AI Market Intelligence System
Illuminati Terminal is an advanced, Python-based financial analytics suite designed to automate the daily workflow of a quantitative analyst. It aggregates unstructured news data, performs deep fundamental and technical valuations on Indian equities (NSE), and uses Generative AI (Google Gemini) to produce institutional-grade investment strategies.

🚀 Key Features
1. 🧠 AI-Powered "Trend Hunter" Engine
Instead of reacting to price moves, the terminal reads the news to predict future sector rotation.

Semantic Scanning: Asynchronously scans thousands of headlines from Economic Times, Reuters, Bloomberg, Livemint, and a custom Google News Proxy (to catch live updates from Moneycontrol).

Hype Scoring: Detects emerging macroeconomic themes (e.g., "Green Hydrogen," "Defense," "Semiconductors") by analyzing keyword density across millions of data points.

Output: Generates a "Future Booming Industries" table, quantifying which sectors are capturing the narrative market share.

2. 🛡️ Self-Healing Architecture
Built for stability across any environment (Local PC, Cloud Server, Google Colab).

Auto-Dependency Resolution: On startup, the script performs a self-diagnostic. If libraries like nselib, trafilatura, or yfinance are missing, it automatically installs them without user intervention.

AI Fallback Matrix: If the primary Google Gemini model fails (e.g., 404 error), the system instantly reroutes the request to backup models (gemini-1.5-pro → gemini-pro → gemini-1.0) to ensure you always get your analysis.

Database Hygiene: Automatically manages and cleans SQLite schemas to prevent data corruption during upgrades.

3. 📊 "Omniscient" Analysis Lab
The core valuation engine that fuses three distinct disciplines into a single "Illuminati Score" (0-100):

Deep Fundamentals: Calculates the Intrinsic Value using a Discounted Cash Flow (DCF) model. If cash flow data is sparse, it intelligently switches to a Graham/PE-based valuation.

Deep Technicals: Analyzes trend structure (SMA50/SMA200), Momentum (RSI, MACD), and Volatility (Bollinger Bands, ATR).

Risk Metrics: Computes institutional risk ratios (Sharpe Ratio, Sortino Ratio, Max Drawdown) to penalize volatile assets even if they are trending up.

Stress Testing: Simulates portfolio performance under specific macroeconomic shocks (e.g., "Oil Price Shock" for energy stocks).

4. ⚖️ Balanced "Bearish" Logic
Unlike simple screeners that only look for buys, Illuminati v16.0 acts as a risk manager.

Punitive Scoring: The algorithm actively subtracts points for red flags (e.g., -20 for Downtrend, -15 for Overbought RSI, -10 for Overvaluation).

Dual Reporting: Clearly separates the market into 🚀 Top Opportunities (Buys) and ⚠️ Warnings & Exits (Sells), helping you protect capital as well as grow it.

5. 📝 Executive Reporting Suite
Delivers insights in every format you need:

Interactive HTML Dashboard: A searchable, filterable web report containing news feeds, strategy tables, and sector heatmaps.

Excel Strategy Sheet: A raw data file for further quantitative modeling.

Full Deep Dive (Text File): A transparent "math receipt" for every single stock analyzed, showing the exact formula used to derive its Target Price and Score.

Auto-Emailer: Packages all reports and sends an Executive Briefing to your inbox automatically after every run.

⚙️ How It Works in Real Life (The Workflow)
Imagine running this script at 08:00 AM before the market opens. Here is the autonomous sequence it executes:

The Wake-Up & Self-Check: The script initializes, verifies its environment, and auto-installs any missing dependencies. It connects to the database and cleans up old temporary files.

The "Wide Net" Cast (Data Ingestion):

It triggers an asynchronous crawler that hits 8+ global financial feeds simultaneously.

It scrapes the full body text of articles (not just headlines) to understand context.

Entity Resolution: It reads a headline like "Tata Motors plans new EV gigafactory" and uses the nselib database to map "Tata Motors" to the specific ticker TATAMOTORS.NS.

The Analysis Crunch (The "Brain"):

For every identified ticker, it pulls real-time price data via a Waterfall Engine (trying TwelveData first for precision, falling back to Yahoo Finance).

It runs the DCF Valuation to see if the stock is cheap.

It runs the Technical Scanner to see if the stock is moving.

It calculates the Sharpe Ratio to see if the stock is risky.

Result: It determines TATAMOTORS is a "STRONG BUY" with a target of ₹1,250 based on a 15% undervaluation and strong momentum. Conversely, it marks WIPRO as a "SELL" due to declining momentum and overvaluation.

The AI Analyst (Generative Insight): The system feeds the raw data tables into Google Gemini. The AI writes a human-readable summary, explaining why certain sectors are popping and connecting the dots between news (e.g., "Semiconductor incentives") and stock picks.

The Dispatch:

It saves a .xlsx file for your records.

It generates a .html dashboard for quick viewing.

It compiles a Deep_Dive.txt file proving its math.

Final Step: It emails this entire package to your phone.

The Result: You start your trading day with a complete, mathematically rigorous hedge fund briefing—generated entirely while you were getting coffee.

🛠️ Installation
1. Clone the Repository

Bash

git clone https://github.com/yourusername/illuminati-terminal.git
cd illuminati-terminal
2. Install Dependencies (The script handles this automatically, but you can do it manually):

Bash

pip install -r requirements.txt
3. Set Up API Keys (Optional but Recommended) You can run the script interactively and enter keys when prompted, or set them as environment variables:

GEMINI_API_KEY: For AI narratives.

TWELVEDATA_KEY: For premium data feeds.

EMAIL_USER / EMAIL_PASS: For the auto-emailer features.

4. Run It

Bash

# Standard interactive mode
python illuminati_terminal.py --interactive

# Schedule mode (Runs daily at 08:00 AM)
python illuminati_terminal.py --schedule
