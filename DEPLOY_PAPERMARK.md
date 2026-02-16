# Deploying Your Partner Portal (Papermark)

This guide will help you launch your own secure "Data Room" for sharing tax returns and P&L statements.
We will use **Papermark** (Open Source DocSend) and host it for free on **Vercel**.

## Step 1: Deploy to Vercel
1.  Click this button to deploy your own copy of Papermark:
    [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fmfts%2Fpapermark&env=NEXT_PUBLIC_BASE_URL,NEXTAUTH_SECRET,DATABASE_URL)

2.  **Configure Project**:
    -   **Project Name**: `investor-mergim-docs` (or similar).
    -   **Database**: Select "Create" (Vercel Postgres) when prompted. It's free.
    -   **Environment Variables**: Vercel will ask for `NEXTAUTH_SECRET`. You can generate one by running `openssl rand -base64 32` in your terminal or just typing a random long string.

3.  Click **Deploy**.
    -   Wait for the "Check" marks. It might take 1-2 minutes.

## Step 2: Connect Your Domain
1.  Once deployed, go to the **Settings** tab in your new Vercel project.
2.  Go to **Domains**.
3.  Add `docs.investormergim.com`.
    -   Vercel will give you a **CNAME** record value (usually `cname.vercel-dns.com`).

## Step 3: Update Your DNS (Where you bought your domain)
1.  Log in to your Domain Registrar (GoDaddy, Namecheap, Google Domains, etc.).
2.  Go to **DNS Settings**.
3.  Add a new record:
    -   **Type**: `CNAME`
    -   **Name**: `docs`
    -   **Value**: `cname.vercel-dns.com` (or whatever Vercel gave you).
    -   **TTL**: `Auto` or `3600`.

## Step 4: You're Live!
-   Go to `https://docs.investormergim.com`.
-   Create an account (you are now the Admin).
-   Upload your documents (Tax Returns, P&L).
-   Generate secure links and share them with banks!

*Note: Your main site (`investormergim.com`) already has a "Partner Login" button that points to this new portal.*
