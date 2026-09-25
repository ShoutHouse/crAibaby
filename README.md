# crAibaby

A project that aims to bring the mirror to the party.

If you're a high horsin', entitled, ... well... ANYTHING, or sell your trade/product for an unrealistic price, AND THEN expect others to maintain that status for you, it should be known that no entity should put forth any modicum of effort into accommodating you. From what I can tell, the reason being… just because you… exist? If you can't hack it without gatekeeping, then you can't hack it in any reality that we're in. 

crAibaby is an automated pipeline that scrapes the internet for people crying about market efficiency, Ai eating their lunch, or local business guilt trips. When somebody posts some "wah wah cry cry" garbage about how the world owes them a living or a $15,000 bug bounty, on their schedule, or to buy “local” only to have a shop full of trinkets from temu and AliExpress… then this system finds it, scores it, takes a screenshot, and archives the receipt; which should provide a nice clean account of the biggest whiners in any given niche.

**The Catalyst:** A massive thank you to Andy Nguyen (The Flow) for being the spark that lit this project. Whining about someone else finding “your” zero-day bugs before you were ready to cash them in is the exact gatekeeping energy that willed crAibaby into existence. 

## How it works

The whole flow is built to run autonomously without babying it.

1. **Ingestion Layer:** Monitors targeted feeds (YouTube comment sections, subreddits, local op-eds) for high-density complaining.
2. **Analysis Layer:** Passes the text to a lightweight model. If the logic is stupid and flawed and flags as pure gatekeeping or entitlement, it gets queued.
3. **Result Layer:** Spins up a headless Playwright instance, navigates to the exact comment or post, and renders a high-res DOM snapshot before the user can delete it.
4. **CrAiers List:** Generates a structured JSON entry, pairs it with the screenshot, and builds out to a static gallery.

## Tech Stack

For:
* **Scraping & Capture:** Python, Playwright
* **Brain:** OpenAI or Gemini API
* **Storage:** Local JSON and a lightweight object store
* **Frontend:** Astro (hosted on GitHub Pages)

## Setup

1. Clone this repo.
2. `pip install -r requirements.txt`
3. Drop your API keys into a `.env` file.
4. Run the daemon and let it hunt.
