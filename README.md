# shopify-checkout-ui-extention-doc
Follow steps to create shopify Checkout extentions to modify checkout page..!

# Quick checklist before you start (ticklist)
-> Shopify Partner account (done) or shopify plus plan 
-> Dev store with Checkout Extensibility / Plus sandbox (if you need shipping/payment extension points)
-> Node.js (20.10+) + npm/pnpm/yarn + Git
-> Shopify CLI installed & logged in (shopify login --store your-dev-store.myshopify.com)
-> Code editor (VS Code)

# What is Shopify CLI?
  Shopify CLI = a command-line tool made by Shopify.
  It helps you create apps, generate checkout extensions, run them locally, connect to your dev store, and deploy.
  Without Shopify CLI, you’d have to manually configure tunnels, uploads, app versions — very messy.
  So, it’s the main tool to build Shopify apps and extensions.

# Why shopify login is necessary?
  Shopify CLI needs permission to connect your local code ↔ Shopify Partner account + Dev store.
  When you run shopify login --store your-store.myshopify.com, it opens a browser, you log in, and then CLI gets an API token to:
  Install your app automatically in the dev store
  Preview extensions in checkout
  Deploy app versions
  👉 Without login, CLI cannot push your extension to Shopify servers.

# Step-by-step commands (macOS/Linux)
# 👉 Step 1: Check if Node.js and Git are installed
node -v         # shows your Node.js version (must be >= 20.10)
git --version   # shows Git version (must be >= 2.28)

If missing:
sudo apt install nodejs npm git -y  
# Ubuntu/Debian

# 👉 Step 2: Install Shopify CLI globally
npm install -g @shopify/cli @shopify/app
# This installs the Shopify CLI tool which is required to create apps and extensions.

# 👉 Step 3: Verify Shopify CLI installation
shopify version
# This will display the installed Shopify CLI version to confirm it’s working.

# 👉 Step 4: Login to your Shopify development store
shopify login --store your-store-name.myshopify.com
# This opens a browser window to log in to your Shopify Partner account.
# 👉 It connects your local project with your dev store so CLI can preview and deploy apps.

# 👉 Step 5: Create a new Shopify app project
npm init @shopify/app@latest my-app
cd my-app
# This scaffolds (creates) a Shopify app project with default files and setup.
# "cd my-app" moves you inside the new app folder.

# 👉 Step 6: Generate a Checkout UI Extension inside the app
shopify app generate extension --template checkout_ui --name my-checkout-extension
# This creates a new folder under "extensions/" with starter code for a checkout extension.
# 👉 This is where you’ll write your extension logic (e.g., showing buttons in checkout).

# 👉 Step 7: Run the app in development mode
shopify app dev
# This will:
# - Open a Cloudflare tunnel
# - Install the app automatically into your dev store
# - Give you a link to preview the checkout extension live in checkout

# 👉 Step 8: (Optional) Serve only the extension
shopify extension serve
# Runs just the extension (instead of the whole app) for faster development.

# 👉 Step 9: Build and deploy your app + extension
shopify app deploy
# This builds your project, creates an "app version" on Shopify’s servers, and deploys it.
# 👉 After this step, your extension can be used in your store or submitted to Shopify.

store ke sath link hona jruri hai, app ko generate krne k baad app install krna jruri hai 

my documentation url : https://docs.google.com/document/d/1pFPqnyFPXe18hg4KEvhBb4-9G0HK1UKiyDVYTgsZT6I/edit?tab=t.0





