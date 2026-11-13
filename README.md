# titanhold-ckb-pay

**Status: planned prototype / work in progress. This is not a live payment product. It is not running on CKB mainnet. Do not send real funds to anything in this repository.**

A planned open-source checkout integration that would let clients of [TITANHOLD](https://titanhold.app) pay for work (sites, bots, and AI-agent orders taken by Amanda, TITANHOLD’s AI assistant, and by the client Telegram bot) using the Nervos CKB network.

This repository is the public work area for a CKB Eco Fund Spark Program proposal. Implementation has not started beyond this description. There is no payment server, no wallet integration, and no contract to use in production.

## Who this is for

- TITANHOLD is a development studio and platform for small businesses. Amanda takes the order in chat, gives a written quote, and the platform builds the site, bot, or AI agent. Clients can see a demo on their own data before they pay.
- Today, clients pay by invoice/bank or in USDT (TRC20). Licensed payment providers are in talks, not signed. Other payment rails at TITANHOLD are prototypes, not licensed production systems.
- This project’s scope is a **CKB payment/checkout adapter** for that existing order flow — not a rewrite of the whole platform, and not a claim that TITANHOLD already accepts CKB.

## Planned scope (Spark period, about 6 weeks)

In scope:

1. A documented checkout design: how an order created by Amanda or the Telegram bot would request a CKB payment, show payment status, and mark the order as paid only after a verifiable on-chain (testnet first) payment.
2. A reference implementation using official CKB developer tools (planned: the CCC JavaScript SDK and a supported wallet such as JoyID, on **CKB testnet** first).
3. A small demo path a reviewer can run: create a sample order, request a testnet payment, confirm it, and see the order state change. Verification should not require reading the entire codebase.
4. English documentation: architecture, how to run the demo, how to verify a payment, and a clear list of what is still out of scope.

Out of scope for this prototype:

- Production / mainnet deployment, or any invitation to pay with real CKB or real client money.
- A licensed escrow business or a claim that TITANHOLD already holds funds as a licensed escrow agent.
- Replacing invoice, bank, or USDT payment options that clients already use.
- Token issuance, trading, or financial speculation.

## Milestones

| Week | Goal |
|---|---|
| 1 | Write the checkout flow and module boundaries. Confirm testnet tooling (CCC, wallet connect, how a payment is uniquely tied to an order). |
| 2 | Scaffold the repo so a reviewer can install and run a stub server. Implement testnet wallet connect and a payment request for a dummy order. |
| 3 | Record a testnet payment against an order id and update order status only after verification. Add automated checks where practical. |
| 4 | Adapter interface for the Amanda / web checkout path (how TITANHOLD would call this module). No claim that it is already wired into production. |
| 5 | Adapter for a Telegram-bot payment link (same payment request, different surface). |
| 6 | Documentation, a short demo recording or scripted walkthrough, and a completion note that compares this plan with what actually shipped. |

If a step slips, the work is narrowed rather than quietly declared live.

## Current state versus this plan

- **Now:** this public repository, a MIT license, and a written plan. TITANHOLD itself is a live studio at https://titanhold.app with paying clients. That is separate from this CKB work.
- **After a Spark grant (if awarded):** the items in the milestone table, on testnet, in this repository.
- There is no CKB integration in the TITANHOLD platform today.

## Honest company facts (not fundraising claims)

TITANHOLD LLC (Wyoming, USA) was organized on 14 October 2026. Solo technical founder: Hennadii Kovalenko. Traction of the studio (not of this prototype): $18,200 received from 5 paying clients, 2 repeat clients, 2 on monthly support, $0 raised. This project does not claim ARR, and it does not claim to be live on any mainnet.

## Security

- Do not put private keys, mnemonics, `.env` secrets, or production credentials in this repository.
- Any example config should use public testnet values and throwaway addresses only.
- Reviewers should never send mainnet funds when trying a demo.

## License

MIT. See [LICENSE](LICENSE).

## Contact

- Site: https://titanhold.app
- Email: hennadii@titanhold.app
- GitHub: https://github.com/wolkodaww123-ctrl
- Nervos Talk: https://talk.nervos.org/u/hennadii
