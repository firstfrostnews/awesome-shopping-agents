# Awesome Shopping Agents

Open-source tools for letting an AI agent find, compare, book and pay for things on your behalf, from the buyer's side.

We read the code of every project here, and each description says what the code actually does, not what the README promises.

Most of these tools stop at the cart and leave the last click to you. A few say they ask before paying, but the "yes" is a flag or token the agent can supply itself. Only two enforce the question in code. Check the payment tag before you let an agent near your card.

**Payment:** `🙋 you pay` = the agent never presses pay; it fills the cart or stops at checkout · `✋ asks first` = the code blocks payment until you approve, and the agent can't approve for itself · `⚠️ asks on paper` = there is a confirmation, but it's a flag, a self-issued token or a line in the docs, so the agent can say yes for you · `❗ no ask` = places orders without asking

**Money:** no tag = the tool talks to the store directly and takes no cut · `hosted` = requests, and sometimes your money, go through the maker's own servers · `affiliate` = links carry the maker's referral code by default · `affiliate API` = built on an affiliate network, so every result is a referral link

**Status:** `ready` = usable as is · `adapt` = needs setup or code changes · `infra` = a building block for developers · `verify` = unfinished or unclear; check the code yourself

`no license` = no license file, so you can't legally reuse the code.

## Contents

- [Shop for you](#shop-for-you)
- [Find, compare and watch prices](#find-compare-and-watch-prices)
- [After you buy](#after-you-buy)
- [Wallets and spending limits](#wallets-and-spending-limits)
- [Receipts](#receipts)
- [Traps](#traps)
- [Building blocks](#building-blocks)
- [Test your agent](#test-your-agent)
- [Related lists](#related-lists)

## Shop for you

- [Open Supermarkets](https://github.com/abracadabra50/open-supermarkets) - One CLI, HTTP API and MCP server for supermarkets in the UK, Ireland, the Netherlands, Belgium, Spain, Hungary, the US and Canada. Search, cart and delivery slots; Tesco and Sainsbury's checkout opens a browser and stops at payment. `TypeScript` · `Self-host` · `ready` · `🙋 you pay`
- [Mika](https://github.com/wangzan101/Mika) - On-device Android agent that operates any app on a hidden background screen. Asks before placing an order and never taps the payment button itself; other actions, like sending messages, run without asking. Needs wireless-debugging pairing and sideloading. `Kotlin` · `Android` · `adapt` · `🙋 you pay`
- [kroger-mcp](https://github.com/CupOfOwls/kroger-mcp) - Kroger products, stores and your real cart through Kroger's public API. You check out on Kroger's site. `Python` · `MCP` · `ready` · `🙋 you pay`
- [grocery-cli](https://github.com/jgalea/grocery-cli) - Searches several countries' supermarkets, matches the same product across stores and compares prices; some stores can fill your cart. You pay in the browser. `Go` · `CLI` · `MCP` · `ready` · `🙋 you pay`
- [northcinder](https://github.com/cinderline/northcinder) - Local shopping MCP that searches several stores, explains its ranking and keeps an audit log. Before a purchase it shows merchant, items and total and waits for a one-time code only you can see; automatic checkout needs a store that supports ACP, otherwise you get a cart link. Gained 1,200 stars in five days, then stopped updating. `TypeScript` · `MCP` · `verify` · `✋ asks first`
- [mcd-cn-assistant](https://github.com/junxchan54-maker/mcd-cn-assistant) - Skill files for McDonald's China's remote MCP: deals, coupons, best-price combos and group orders. The order tools live on the remote server; "list the items and confirm" is an instruction in the docs, not code. Whether the MCP is official is unconfirmed. `Skill` · `MCP` · `verify` · `⚠️ asks on paper` · `hosted`
- [texas-grocery-mcp](https://github.com/mgwalkerjr95/texas-grocery-mcp) - H-E-B (Texas) products, stores, coupons and cart. Previews before adding to the cart and reads the cart back after; the preview switch is a parameter the agent can turn off. `Python` · `MCP` · `ready` · `🙋 you pay`
- [orderwise-agent](https://github.com/ucloud/orderwise-agent) - Drives several Android phones to put the same food order into Meituan, JD and Taobao Shangou and compares packing, delivery and total cost at checkout. Stops there by prompt, not by a hard rule. Needs AutoGLM and cloud or local phones. `Python` · `Android` · `adapt` · `🙋 you pay`

By country:

- 🇪🇸 [mercadona-cli](https://github.com/ivorpad/mercadona-cli) - Mercadona search, cart, delivery slots and real order submission. Refuses to submit without `--yes`, which the agent can pass. `Go` · `CLI` · `ready` · `⚠️ asks on paper` · `no license`
- 🇨🇿 [rohlik-mcp](https://github.com/tomaspavlin/rohlik-mcp) - Rohlik products, deals, delivery, past orders and your real cart. `TypeScript` · `MCP` · `ready` · `🙋 you pay`
- 🇨🇿 [alza-mcp-community](https://github.com/lukabudik/alza-mcp-community) - Alza catalog, account, cart, delivery, orders, returns and payment. Can submit a real order; each order action needs a one-time token the agent requests itself. Store links carry UTM attribution by default (disclosed). `TypeScript` · `MCP` · `ready` · `⚠️ asks on paper`
- 🇨🇭 [migros-mcp](https://github.com/lewpgs/migros-mcp) - Migros products, recipes, orders, coupons and your shopping list and basket; hands you a Migros link to finish. `TypeScript` · `MCP` · `ready` · `🙋 you pay` · `no license`
- 🇩🇰 [handle-mcp](https://github.com/NJohansen/handle-mcp) - Nemlig and BilkaToGo: products, recipes, deals and basket price comparison; edits your real basket. `Python` · `MCP` · `ready` · `🙋 you pay`
- 🇩🇰 [bilkatogo-mcp](https://github.com/tkjaergaard/bilkatogo-mcp) - BilkaToGo catalog, substitutes, cart and delivery slots. `TypeScript` · `MCP` · `CLI` · `ready` · `🙋 you pay`
- 🇮🇳 [blinkit-mcp](https://github.com/hereisSwapnil/blinkit-mcp) - Drives Blinkit in Firefox: OTP login, address, search, cart and checkout. Can press the final button on cash on delivery with no confirmation step; UPI still needs you. `Python` · `MCP` · `adapt` · `❗ no ask`

Use with care:

- [LetsFG](https://github.com/LetsFG/LetsFG) - Flight and hotel search and booking through LetsFG's servers; `book_flight` sends the booking without a separate approval. Server code isn't public. MIT with optional commercial terms. `Python` · `MCP` · `CLI` · `verify` · `❗ no ask` · `hosted`
- [mcp-server-amazon](https://github.com/rigwild/mcp-server-amazon) - Searches Amazon and edits your real cart using cookies you export. Its "checkout" tool doesn't contact Amazon and only replies "Purchase confirmed", so your agent may tell you something was bought when it wasn't. `TypeScript` · `MCP` · `adapt` · `🙋 you pay`

## Find, compare and watch prices

- [PriceBuddy](https://github.com/jez500/pricebuddy) - Self-hosted price and stock tracker with history and drop alerts. `PHP` · `Self-host` · `ready` · `affiliate` (can be turned off)
- [PriceGhost](https://github.com/clucraft/PriceGhost) - Self-hosted price and stock tracker; several extraction methods vote on the price, optionally checked by a model. `TypeScript` · `Self-host` · `ready` · `no license`
- [Discount Bandit](https://github.com/Cybrarist/Discount-Bandit) - Multi-user self-hosted price tracker for Amazon, AliExpress, eBay and more. `PHP` · `Self-host` · `ready` · `no license`
- [flight-finder](https://github.com/affromero/flight-finder) - Self-hosted flight, hotel and car-rental price tracking with alerts for new lows. `TypeScript` · `Self-host` · `ready`
- [GooFish-AIMonitor](https://github.com/tristanwqy/GooFish-AIMonitor) - Watches Xianyu (闲鱼) listings with rules and an optional model check; alerts on price drops and sell-outs. Runs locally. `Python` · `Self-host` · `ready`
- [swissgroceries-mcp](https://github.com/nicktcode/swissgroceries-mcp) - Products, promotions and stock across eight Swiss chains with unit prices normalized; plans single- or multi-store shopping lists. `TypeScript` · `MCP` · `ready` · `restricted license` (PolyForm Shield)
- [torob-mcp](https://github.com/mmdju/torob-mcp) - Read-only Torob (Iran) search, price history, offers and shop details. `TypeScript` · `MCP` · `ready`
- [aliexpress-mcp-server](https://github.com/justinritchie/aliexpress-mcp-server) - Read-only AliExpress search, product details, shipping to your country and your cart, using your cookies. `Python` · `MCP` · `ready` · `no license`
- [amazon-in-mcp](https://github.com/justadityaraj/amazon-in-mcp) - Read-only Amazon India search: cheapest in stock, ratings and a simple value score. `TypeScript` · `MCP` · `ready` · `affiliate` (can be turned off)
- [price-hunter](https://github.com/h382110229/price-hunter) - Taobao, JD and Pinduoduo price comparison and coupons through the three affiliate networks. `Python` · `MCP` · `adapt` · `affiliate API` · `no license`
- [buywhere-mcp](https://github.com/BuyWhere/buywhere-mcp) - Bridge to BuyWhere's hosted product search; nothing runs locally. `TypeScript` · `MCP` · `verify` · `hosted`
- [shopsavvy-mcp-server](https://github.com/shopsavvy/shopsavvy-mcp-server) - Bridge to ShopSavvy's hosted product and price lookup. `TypeScript` · `MCP` · `verify` · `hosted`
- [idealo MCP guide](https://github.com/idealo/mcp-server-guide) - Setup guide and tool schemas for idealo's hosted price-comparison MCP; no server code. `Docs` · `MCP` · `verify` · `hosted`

## After you buy

- [Haq](https://github.com/Shukla070/Haq) - Takes screenshots, bills and voice notes about a failed UPI debit or an online refund in India, works out where to complain and drafts the complaint. You send it and confirm the refund yourself. `Python` · `Web` · `Android` · `adapt` · `no license`
- [costco-price-match](https://github.com/awsdataarchitect/costco-price-match) - Reads your Costco receipt with AWS Bedrock, gathers price-drop tips from forums, coupon books and Reddit, and reports items you may be able to claim back. Web page and scheduled email. `Python` · `Web` · `adapt` · `no license`
- [Pactwright Kit](https://github.com/Pactwright/Pactwright-Kit) - SDK and MCP tools for refundable agent purchases: the payment sits in escrow on Stellar until delivery is verified. The "manual" gate approves by default and the dispute tool isn't wired up yet. `TypeScript` · `MCP` · `infra` · `crypto`
- [Pactwright contracts](https://github.com/Pactwright/Pactwright-contracts) - The Soroban escrow contract behind Pactwright: locks the buyer's capped amount, releases or refunds on a verifier's ruling. `Rust` · `Stellar` · `infra` · `crypto`

## Wallets and spending limits

- [Steward](https://github.com/Steward-Fi/steward) - Self-hosted agent wallet and credential proxy; a policy engine blocks signing or requests over your limits and sends them to a human approval queue. `TypeScript` · `Self-host` · `infra`
- [AgentCard MCP](https://github.com/tiny-agent-company/mcp) - Creates and closes prepaid virtual cards; card details need approval, but the same MCP has a tool that can resolve the approval, so the agent may approve itself. `TypeScript` · `MCP` · `verify` · `hosted`
- [x402card](https://github.com/RWA-ID/x402card) - Maps spending rules to virtual-card controls with approvals, merchant checks and freezes. Runs on Airwallex's sandbox. The new agent token is kept out of the text reply but still sits in the structured response. `TypeScript` · `Cloudflare` · `infra` · `hosted`

## Receipts

- [Signet](https://github.com/Prismer-AI/signet) - Signs a receipt for every agent action, with verification, audit chain, delegation and policies. A receipt proves what the agent said it did, not that a payment cleared. `Rust` · `MCP` · `CLI` · `infra`
- [receipt-protocol](https://github.com/hhh7666/receipt-protocol) - Issues signed, verifiable receipts for actions an agent reports. `JavaScript` · `Cloudflare` · `infra` · `no license`

## Traps

- [Mandate-Shield](https://github.com/LSUDOKO/Mandate-Shield) - Checkpoint before a shopping agent signs a payment mandate: amount match, required fields, replay and identity checks. Its demo catches a product page that hides "limit already approved" text. `TypeScript` · `MCP` · `adapt`
- [llm-rank-optimizer](https://github.com/aounon/llm-rank-optimizer) - Research code showing that a short string added to a product page can push it to the top of an AI's recommendations. `Python` · `research`

## Building blocks

- [phone-for-ai](https://github.com/lllq-123/phone-for-ai) - Self-hosted remote control for an Android phone: pairing, screen stream, taps and typing, app launch and a command queue. `Java` · `Android` · `MCP` · `infra`

## Test your agent

- [ACES](https://github.com/mycustomai/ACES) - Mock store for studying what an AI shopper picks when you change product position, labels, ratings and prices. `Python` · `research` · `no license`
- [Magentic Marketplace](https://github.com/microsoft/multi-agent-marketplace) - Simulated market of buyer and seller agents; measures welfare, fairness and efficiency, and how well agents resist manipulation. `Python` · `research`
- [WebMall](https://github.com/wbsg-uni-mannheim/WebMall) - Benchmark with several local web shops: can a web agent find and compare offers, fill the cart and check out, including vague requests and cheaper substitutes. `Python` · `research` · `no license`

## Related lists

These cover the seller side: protocols, SDKs and tools for selling to agents.

- [Merit Systems' awesome-agentic-commerce](https://github.com/Merit-Systems/awesome-agentic-commerce)
- [MentionNetwork's awesome-agentic-commerce](https://github.com/MentionNetwork/awesome-agentic-commerce)
- [damoahdominic's awesome-agentic-commerce](https://github.com/damoahdominic/awesome-agentic-commerce)
- [awesome-agentic-payments](https://github.com/bitrefill/awesome-agentic-payments)
- [awesome-x402](https://github.com/xpaysh/awesome-x402) - Pay-per-request crypto payments for agents.
- [iran-mcp](https://github.com/sepehr071/iran-mcp) - Directory of MCP servers for Iranian services.

## Contributing

Every entry needs a code read, a one-line description of what the code does, and the tags above. We don't list tools that need you to buy or hold the maker's own coin, swap in referral links without saying so, or cripple the free version. A maker that has a coin but whose tool works without it gets an `own coin` tag. Seller-side tools go to the related lists.

## License

This list is licensed under [CC BY 4.0](LICENSE). You may copy, adapt and republish it, including commercially, as long as you credit **Awesome Shopping Agents** and link to <https://github.com/firstfrostnews/awesome-shopping-agents>.

---

From [First Frost](https://firstfrost.news), a scored weekly watch on the agent economy.
