# 🚀 Crypto Watcher: Real-Time Telegram Alerts + Supabase Logging + Lovable Dashboard  

## 📌 Category  
**Finance / Market Monitoring**  

---

## 📝 Detailed Description  
The crypto market is highly volatile, and traders risk missing profitable opportunities or losses if they don’t get timely updates. Manually refreshing charts is inefficient and stressful.  

**Crypto Watcher** automates real-time crypto monitoring using **Make.com**.  
- Fetches live data from the **CoinGecko API**  
- Applies filtering rules (e.g., alert if 24h price change ≥ 5% or ≤ -5%)  
- Instantly sends formatted alerts to **Telegram**  
- Logs all monitored data into **Supabase** for storage and history  
- Displays insights in a **Lovable-powered dashboard** for visualization  

### 🎯 Who It’s For  
- Traders needing instant awareness of market swings  
- Crypto enthusiasts tracking daily volatility  
- Portfolio managers monitoring multiple coins with history and charts  

✅ **Expected outcomes**:  
- Immediate Telegram alerts when significant price changes occur  
- Historical logging of crypto metrics for later analysis  
- A live dashboard for tracking trends in real time  

---

## ⚙️ How It Works (Functionality)  
1. **Trigger**  
   - Webhook in Make.com (manual trigger or scheduled via cron).  

2. **Fetch Crypto Data**  
   - HTTP GET → CoinGecko `/coins/markets` endpoint  
   - Parameters:  
     - `vs_currency=usd`  
     - `ids=bitcoin,ethereum,...`  
     - `price_change_percentage=24h`  

3. **Filtering & Logic**  
   - If `price_change_percentage_24h >= 5` or `<= -5` → continue  
   - Else → stop execution  

4. **Send Notification (Telegram)**  
   - **Telegram Bot Module** delivers an alert:  
     ```
     🚨 Crypto Alert 🚨
     Coin: {{name}} ({{symbol}})
     Price: ${{current_price}}
     24h Change: {{price_change_percentage_24h}}%
     Market Cap: ${{market_cap}}
     Volume: ${{total_volume}}
     Updated: {{last_updated}}
     ```

5. **Log Data (Supabase)**  
   - Insert row into Supabase table with:  
     - Timestamp  
     - Coin name & symbol  
     - Price  
     - % change  
     - Market cap  
     - Volume  
     - Alert triggered (Yes/No)  

6. **Dashboard (Lovable UI)**  
   - Supabase data is connected to a Lovable-generated dashboard.  
   - Dashboard features:  
     - Live coin data (price, change, market cap, volume)  
     - Alert highlights (coins that triggered thresholds)  
     - Charts from Supabase historical logs  
     - Mobile + desktop responsive design  

---

## 🛠 Tools Required  
- [Make.com](https://www.make.com/) (automation workflows)  
- [CoinGecko API](https://www.coingecko.com/en/api) (crypto data, free)  
- [Telegram Bot API](https://core.telegram.org/bots) (alerts)  
- [Supabase](https://supabase.com/) (database & API backend)  
- [Lovable](https://lovable.dev/) (frontend dashboard)

- 
## 📐 Workflow Architecture  
Here’s the pipeline of the automation:  

![Workflow Architecture](https://github.com/AbdulTheAnalyst/Crypto-Watcher-Real-Time-Telegram-Alerts-/blob/main/2.png)  

---

## 📏 Size of Project  
**Large Project**  
- Workflow: Webhook → API Fetch → Filtering → Telegram → Supabase → Lovable Dashboard (**6+ tasks**)  

---

## 🔑 Setup Requirements  
- Make.com account  
- Telegram bot token (via BotFather)  
- CoinGecko API (no key required, just endpoints)  
- Supabase project (with database + API keys)  
- Lovable account (for UI connected to Supabase)  

---

## ⏱ Deployment Time Estimate  
- **Basic setup (Telegram only):** 2–3 hours  
- **With Supabase logging + Lovable dashboard:** 2–3 days  

---

## 💡 Value Proposition  
- Saves ~2–3 hours/day of manual price checking  
- Ensures no missed opportunities during sudden swings  
- Provides history and trends for better decision-making  
- **ROI:** ~$1,200/month in saved time + improved trading insights  

---

## 🎥 Demo Video  
*(Insert Loom/YouTube link showing: webhook trigger → Telegram alert → Supabase log → Lovable dashboard update)*  

---

## ⚠️ Known Limitations  
- CoinGecko API rate limit: 50 calls/minute  
- Telegram bot requires setup via BotFather  
- Supabase free tier has database/storage limits  
- Lovable dashboard depends on Supabase connection stability  

---

## 📌 Testimonials / Use Cases  
- **Trader:** Receives Telegram alert when BTC moves ±5% in 24h, then checks dashboard for history.  
- **Portfolio Manager:** Uses Supabase data + Lovable UI to review weekly market swings.  
- **Crypto Enthusiast:** Tracks multiple coins visually without switching apps.  

---

## 📊 Size Classification  
**Large Project**  

---

## 💰 Estimated ROI  
- Hours saved: ~60–80/month  
- Value: ~$1,200–$1,600/month  
- Minus <$100 setup/infrastructure costs → **Net ROI ≈ $1,100–$1,500/month**  

---

## 🗂 Version & Updates  
- **v1.0** – Initial release (Webhook → CoinGecko → Telegram)  
- **v1.1** – Added Supabase logging  
- **v1.2** – Integrated Lovable UI dashboard  
- **v1.3** – Added charts + historical insights from Supabase  

---
