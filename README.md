# RiseBot — RisePro™ Public Chatbot

A small public-facing RisePro™ customer support chatbot built with Streamlit and the OpenAI API.

## Run locally

1. Install Python 3.10 or newer.
2. Unzip the project and open a terminal in the project folder.
3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Set your API key as an environment variable (do not put it in `app.py`):

   **macOS/Linux**
   ```bash
   export OPENAI_API_KEY="your-api-key"
   streamlit run app.py
   ```

   **Windows PowerShell**
   ```powershell
   $env:OPENAI_API_KEY="your-api-key"
   streamlit run app.py
   ```

The local app opens in your browser. Keep the terminal running while testing.

## Deploy publicly

One simple option is Streamlit Community Cloud:

1. Create a GitHub repository and upload `app.py` and `requirements.txt`.
2. In Streamlit Community Cloud, create a new app from that repository and select `app.py`.
3. In the app's **Secrets** settings, add:

   ```toml
   OPENAI_API_KEY = "your-api-key"
   OPENAI_MODEL = "gpt-4o-mini"
   ```

4. Deploy. Share the generated public app URL with customers.

Never commit API keys to GitHub or expose them in browser-side code. Check current hosting-provider terms, privacy settings, and pricing before launching.

## Before launching to real customers

- Add a privacy notice explaining what data is sent to the AI provider and how chat data is handled.
- Decide whether conversations should be stored; this starter keeps chat history in the user's Streamlit session and does not implement a business CRM.
- Add rate limits, abuse protection, monitoring, and a budget limit for API usage.
- Confirm all product, allergen, nutrition, pricing, subscription, and shelf-life statements with the brand's approved materials.
- The knowledge base contains indicative/target pricing and does not provide a live inventory, order lookup, checkout, shipping calculator, or subscription management integration.
- The app does not send emails or place orders; it directs customers to the relevant support address.
- This is a starter implementation, not a security or regulatory audit.
