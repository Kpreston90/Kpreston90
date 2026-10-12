# Kyle Hawari

Product lead. I decide what gets built, specify it precisely enough to be built,
and find the bug in production before a customer does.

Most recently: a property management system that replaced a commercial SaaS
product at [Metro Mutts](https://www.metromutts.com), a dog daycare and boarding
business in Tulsa — and the books, the bank feed and the front-desk workflow
that go with it. I'm a partner there.

📍 Tulsa / Taos · ✉️ kyle.hawari@gmail.com

---

## Alpha — replacing a commercial PMS, in production

Metro Mutts runs on a product called Gingr: bookings, kennels, check-in,
invoicing, customer records. Alpha replaces it, and runs beside it today while
the front desk moves over.

**Four months. ~680 pull requests. 5,689 tests.** Live, against a real building
— 19 boarding kennels, 80 daycare places, around 50 dogs a day.

What it does:

- **Front desk** — the day's board, check-in and check-out, kennel assignment,
  a vaccination and agreement gate that can be overridden by whoever is standing
  there at 7am, because there is no manager at 7am
- **Money** — invoicing, card payments, packages and a weekly membership, and a
  double-entry ledger that replaces the business's accounting software
- **The business** — cash-flow forecasting off the ledger, customer retention,
  marketing attribution from first enquiry to first booking

Integrations: Gingr (read-only), Plaid, Stripe, Gmail, MailerLite, Google Ads,
Twilio.

### Decisions I'd defend in an interview

**One price list.** Prices lived in four places and three of them disagreed, so a
$30 bath was quoted on screen and a $70 groom charged at the till. Now there is
one editable list and nowhere else for a number to come from.

**Practice money never touches the real books.** Letting staff rehearse on real
customers meant real invoice and payment rows. Rather than filtering them out
everywhere — one forgotten filter and a month of invented revenue lands in the
P&L — practice money is written to a separate ledger that no screen can reach.
Isolation by construction, not by remembering.

**A failed read is never a zero.** A bank balance that can't be read shows "—",
not "$0". We mailed a partner "$0 available" once from an account nobody had
successfully read. Now every figure that can't be justified refuses to render
and says why.

**Shipped less than I was asked for, twice.** Killed a forecasting page with
twenty-five numbers on it because none of them changed a decision; replaced it
with two — the lowest point the account reaches, and the bills causing it.

---

## How I work

I direct AI coding agents and review everything that comes back. That is the
actual job now, and the skill in it isn't prompting — it's specifying behaviour
tightly enough to be unambiguous, and catching the plausible-looking wrong
answer.

Some of what I've caught: a cash-flow screen reading $160,728 in on a month that
sold $35,000, because a query kept the wrong half of every reversed entry. A
home page that white-screened on any cold cache. Books sitting $15,494 under the
real bank balance — not missing money, an opening balance nobody ever set.

I'm the proxy tester. I run the thing in production, click every path, and write
down what breaks.
