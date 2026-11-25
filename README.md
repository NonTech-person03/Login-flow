# Login-flow
New login flow with the updated SVG




New Login Flow Integration
This guide explains how to add the new login flow to a Shopify store.
Step 1: Create the Account Page
1. Log in to Shopify Admin.
2. Go to Online Store → Pages.
3. Click Add Page.
4. Set the page title to user-account.
5. In the page editor, click the HTML (</>) option.
6. Add this code in the Content section:
<div id="sr-headless-account"></div>
7. Save the page.
Step 2: Update the Theme
1. Go to Online Store → Themes.
2. Duplicate the current live theme. This keeps the live theme
   unchanged while you make updates.
3. Open the duplicated theme and click Edit Code.
4. Find and open the sr-checkout.liquid file.
5. Add the following code to the file:
<input type="hidden" id="sellerDomain" value="YOUR-LIVE-DOMAIN.com">

<script>
  window.srAccountPagePath = '/pages/user-account';
  window.accountPortalUrl = 'https://fastrr-login-account.pickrr.com/';
</script>

<script src="https://fastrr-boost-ui.pickrr.com/assets/js/channels/shiprocket-login.js"></script>
Important: Replace YOUR-LIVE-DOMAIN.com with the store's live
domain.

Where to add the code: Add the hidden input and the configuration
settings before the external shiprocket-login.js script. The script
reads these settings when it starts.
Step 3: Create the Account Icon Snippet
1. In the theme code editor, open the Snippets folder.
2. Click Add a new snippet file.
3. Name the file:
   fastrr-account-icon.liquid
4. Add the account icon code to this new file.
5. Save the file.
Note: The account icon code is not included in the supplied
document. Get the correct code separately before completing this step.
Step 4: Add the Account Icon to the Theme
1. Open the theme.liquid file.
2. Find the closing </head> tag.
3. Add this line just above the closing </head> tag:
{% render 'fastrr-account-icon' %}
4. Save the file.
Final Check
Before testing, make sure that:
- [ ] The user-account page has been created and saved.
- [ ] The account page code has been added.
- [ ] The login configuration has been added to sr-checkout.liquid.
- [ ] The live store domain has replaced YOUR-LIVE-DOMAIN.com.
- [ ] The fastrr-account-icon.liquid snippet has been created with
  the correct account icon code.
- [ ] The render line has been added above </head> in
  theme.liquid.
Once all required code has been added, proceed with final testing.
