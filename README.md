# Envelope Budget Tracker

A simple envelope budgeting tool that runs entirely in your web browser — no
install, no accounts, no internet required. It's built for the payday routine of:

1. Take the last two weeks of expenses and **assign each one to an envelope** (category).
2. **Add them up** to see how much cash to pull out.
3. Deposit that cash and pay off the credit card for the stuff you just covered.

Open **`envelope-budget.html`** and you're running. That's the whole program.

## Getting started

1. Download `envelope-budget.html` and double-click it — it opens in your browser.
2. Click **Backup → Load sample data** to see a filled-in example, or start fresh:
   - **Envelopes** tab → add your categories (Groceries, Gas, Car repair…).
   - **Expenses** tab → import a CSV from your bank/card, or add expenses by hand.
   - Assign each expense to an envelope.
   - **Payday** tab → read off the total to withdraw, then click
     **Record payday** to update your balances.

Tip: keep the file in a synced folder (iCloud / Dropbox / Google Drive) and always
open it from there, so it's easy to back up.

## The payday routine, step by step

### 1. Import your expenses
On the **Expenses** tab, click the file picker and choose a CSV exported from your
bank or credit card. The app tries to detect the **date**, **description**, and
**amount** columns automatically — fix them if it guessed wrong. Set whether
charges show up as **negative** numbers (most bank exports) or **positive** numbers
(some card exports). Payments/credits are skipped by default. Duplicate rows you've
already imported are skipped automatically.

No CSV? Use **+ Add one manually**.

### 2. Assign to envelopes
Pick an envelope from the dropdown next to each expense. The first time you assign
something like `SAFEWAY`, the app offers to **remember a rule** so future Safeway
charges auto-assign. Click **Auto-assign by rules** any time to apply them in bulk.

### 3. Read off the total, take out the cash
On the **Payday** tab, the big number is **the total to withdraw**. You choose how
it's calculated:

- **What I spent** — pull cash equal to your actual spending (reimburse exactly).
  Balances stay near zero.
- **Fund to budget** — pull each envelope's fixed per-payday budget instead, so
  money you didn't spend piles up in the envelope for later (sinking funds like
  "Car repair" or "Gifts").

You can use both: budgeted envelopes grow, un-budgeted ones just track spending.

### 4. Record the payday
Click **Record payday & update balances**. This:
- marks that period's expenses as settled,
- updates each envelope's running balance (adds what you funded, subtracts what you
  spent),
- and logs the withdrawal in the **History** tab.

The next period starts automatically with whatever you import next.

## Envelope balances

Every envelope has a running **balance** = money put in − money spent.

- **Reimburse-exactly** envelopes: you fund exactly what you spent, so the balance
  sits at zero.
- **Sinking funds**: give the envelope a per-payday budget (e.g. Car repair $100).
  Record paydays in **Fund to budget** mode and the unspent portion accumulates, so
  when the big repair bill hits, the money's already there.

Use the **Fund** button on any envelope to add or remove money by hand (put in a
negative number to take money out).

## Your data & backups

Everything is stored **in your browser only** (via `localStorage`) — nothing is
uploaded anywhere. That also means clearing your browser data will erase it, so:

- **Backup** tab → **Download backup (.json)** saves a file you can keep.
- **Restore from backup** loads it back, on this or another computer.

**Moving to a new browser or after clearing data?** When you open the app and it's
empty, a **Welcome** prompt appears at the top with a **Restore a backup** button —
click it, pick your `.json` file, and everything comes back. (You can also restore
any time from the **Backup** tab.) Restoring replaces whatever is currently in that
browser with the contents of the backup file.

## Sample CSV

`sample-expenses.csv` is included so you can practice the import step. It's a
typical bank export with quoted descriptions and a payment row that gets skipped.

## Privacy

100% offline. No servers, no tracking, no dependencies. The single HTML file is the
entire application; you can read every line of it.
