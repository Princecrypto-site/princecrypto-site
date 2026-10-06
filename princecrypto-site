import streamlit as st
import pandas as pd
import numpy as np

# 1. PAGE CONFIGURATION
st.set_page_config(
    page_title="Princecrypto.site | Crypto Platform",
    page_icon="⚡",
    layout="wide",
    initial_sidebar_state="collapsed"
)

# 2. CUSTOM CSS (Styling, Fonts & Color Palette)
st.markdown("""
<style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap');
    
    html, body, [class*="css"] {
        font-family: 'Inter', sans-serif;
    }

    /* Main background & accent colors */
    .stApp {
        background-color: #0d1117;
        color: #e6edf3;
    }

    /* Top Navigation Styling */
    div[data-testid="stHorizontalBlock"] {
        background-color: #161b22;
        padding: 10px;
        border-radius: 12px;
        border: 1px solid #30363d;
    }

    /* Crypto Cards & Containers */
    .crypto-card {
        background-color: #161b22;
        border: 1px solid #30363d;
        border-radius: 10px;
        padding: 16px;
        margin-bottom: 12px;
    }

    .crypto-card:hover {
        border-color: #00f2fe;
    }

    /* Brand Green/Cyan Highlights */
    .brand-accent {
        color: #00f2fe;
        font-weight: 700;
    }

    .price-up { color: #00e676; font-weight: 600; }
    .price-down { color: #ff5252; font-weight: 600; }

    /* Custom Metric Styling */
    div[data-testid="stMetricValue"] {
        font-size: 22px;
        color: #ffffff;
    }
</style>
""", unsafe_allow_html=True)

# 3. HEADER & BRANDING
header_col1, header_col2, header_col3 = st.columns([2, 5, 2])

with header_col1:
    st.markdown("### ⚡ <span class='brand-accent'>Princecrypto</span>.site", unsafe_allow_html=True)

with header_col3:
    st.button("Connect Wallet 🔗", type="primary", use_container_width=True)

# 4. NAVIGATION TABS
tabs = st.tabs(["📊 Overview", "📈 Live Markets", "🔄 Trade / Swap", "🏆 Tournaments", "💼 Portfolio"])

# --- TAB 1: OVERVIEW ---
with tabs[0]:
    st.subheader("Market Summary")
    
    # Top Ticker Cards
    m1, m2, m3, m4 = st.columns(4)
    with m1:
        st.metric(label="Bitcoin (BTC)", value="$64,250.00", delta="+2.4%")
    with m2:
        st.metric(label="Ethereum (ETH)", value="$3,480.50", delta="+1.8%")
    with m3:
        st.metric(label="Solana (SOL)", value="$148.20", delta="-0.9%")
    with m4:
        st.metric(label="Binance Coin (BNB)", value="$580.10", delta="+0.5%")

    st.markdown("---")
    
    col_chart, col_orderbook = st.columns([3, 1])
    
    with col_chart:
        st.markdown("### **BTC / USDT Chart**")
        chart_data = pd.DataFrame(
            np.random.randn(30, 1) * 200 + 64000,
            columns=["Price (USD)"]
        )
        st.line_chart(chart_data)

    with col_orderbook:
        st.markdown("### **Order Book**")
        bids_asks = pd.DataFrame({
            "Price (USDT)": [64260, 64258, 64255, 64240, 64235],
            "Amount (BTC)": [0.45, 1.20, 0.88, 2.15, 0.10],
            "Type": ["Ask", "Ask", "Ask", "Bid", "Bid"]
        })
        st.dataframe(bids_asks, hide_index=True, use_container_width=True)

# --- TAB 2: LIVE MARKETS ---
with tabs[1]:
    st.subheader("All Crypto Assets")
    market_df = pd.DataFrame({
        "Asset": ["Bitcoin", "Ethereum", "Solana", "BNB", "XRP"],
        "Symbol": ["BTC", "ETH", "SOL", "BNB", "XRP"],
        "Price": ["$64,250.00", "$3,480.50", "$148.20", "$580.10", "$0.55"],
        "24h Change": ["+2.4%", "+1.8%", "-0.9%", "+0.5%", "+4.1%"],
        "24h Volume": ["$28.4B", "$14.2B", "$3.1B", "$1.1B", "$890M"]
    })
    st.dataframe(market_df, hide_index=True, use_container_width=True)

# --- TAB 3: TRADE / SWAP ---
with tabs[2]:
    st.subheader("Instant Swap")
    c1, c2 = st.columns(2)
    with c1:
        pay_curr = st.selectbox("You Pay", ["USDT", "BTC", "ETH"])
        pay_amt = st.number_input("Amount to Pay", min_value=0.0, value=100.0)
    with c2:
        rcv_curr = st.selectbox("You Receive", ["BTC", "ETH", "SOL"])
        st.number_input("Estimated Amount", value=0.00155, disabled=True)
    
    st.button("Execute Swap", type="primary", use_container_width=True)

# --- TAB 4: TOURNAMENTS ---
with tabs[3]:
    st.subheader("🏆 Trading Tournaments")
    st.info("Next Live Trading Challenge starts in 2 days. Register early to secure your spot!")

# --- TAB 5: PORTFOLIO ---
with tabs[4]:
    st.subheader("Your Portfolio")
    st.write("Connect your wallet to track your live balances and trade history.")
