# Reallyo Rental Leads

Automatically post your rentals to Zillow and Reallyo's other partner rental sites from a chat with Claude. Renters'
inquiries come to you as leads.

Reallyo is rental marketing for property managers, rental agents and brokerages. With this plugin you can ask Claude
to list a new unit with its rent, photos and availability; change the rent or the move-in date; mark a unit rented;
take a listing down; or tell you what's listed and how many more rentals your plan allows. Reallyo checks every listing
before it is saved and tells you which fields to fix. Long-term rentals only.

## What's in the plugin

- **The Reallyo connector**: `.mcp.json` points Claude at Reallyo's MCP server, `https://mcp.reallyo.com`. It has seven
  tools: four that only read (your plan and listing limit, list listings, get one listing, check a listing without
  saving it) and three that change listings (create, update, take down).
- **One skill**, `rental-listings`: how Claude should use those tools, for example finding a listing by its address
  before changing it, asking for missing details rather than inventing them, and confirming before taking a listing
  down.

Nothing else runs on your computer: no scripts, hooks or local servers.

## What you need

A Reallyo account, free or paid; sign up at https://www.reallyo.com if you don't have one. The first time Claude uses the connector, you
sign in with your Reallyo email and password on Reallyo's own page and choose **read only** or **read and write**.
Read-only connections can find and check listings but never change them. Your plan sets how many rentals can be
available at once.

## Data

The plugin sends only what you ask Claude to do with your listings (for example a unit's address, rent and description)
to Reallyo's server at `https://mcp.reallyo.com`, signed in as you. It does not read your chats, files or anything else.
Unusual bulk changes wait for the account holder to confirm by email, and removed listings are kept so they can be
restored.

- Privacy policy: https://www.reallyo.com/privacy-policy
- API terms: https://www.reallyo.com/api-terms

## Example prompts

- "What Reallyo plan am I on, and how many more rentals can I list?"
- "Show me my available rental listings on Reallyo."
- "List my 2-bed at 200 Example Avenue Unit 12, Chicago IL for $2,450 a month, available December 1."
- "Lower the rent on my Unit 12 listing to $2,350 and mark Unit 4A as rented."

## Support

- Email: hello@reallyo.com
- Contact page: https://www.reallyo.com/contact
- Documentation: https://www.reallyo.com/rental-listing-api
- API reference: https://listings-api.reallyo.com/v1/docs

## License

MIT. See [LICENSE](LICENSE).
