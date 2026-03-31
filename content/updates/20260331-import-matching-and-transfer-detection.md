---
title: "Import now detects matches and transfers automatically"
date: 2026-03-31
draft: false
---

Importing bank statements means manually hunting down duplicates and wiring up transfers between accounts. We shipped a fix for that today.

## Duplicate matching

When you import a CSV into an account, OtterFin now checks each row against existing transactions in that account. If it finds an exact amount match within ±3 days, it flags the row with a green **MATCH** badge and shows the existing transaction inline — date, payee, amount, and how many days apart.

On commit, matched rows don't create new transactions — the existing transaction gets marked as matched and its status moves to Posted. In the transaction list, a green MATCH badge marks transactions that came in through an import match, with the original CSV details on hover.

## Transfer detection

Cross-account transfers are trickier. When you import a bank statement, a transfer out of your checking account shows up as a debit — but the corresponding deposit in your savings account is already in the ledger. OtterFin now spots these automatically.

During the import preview, each row is checked against transactions in your other accounts: opposite sign, ±3 days, same household. Cross-currency transfers work too, matched via the original currency and amount. If there's one candidate, it's auto-selected. If there are multiple, you pick which one to link. You can always skip it and import the row as a normal transaction.

On commit, confirmed transfers create a TransferLink between the two transactions and both are marked as transfers. They show up with a blue **TRNSFR** badge in the transaction list.

## Potential duplicate flagging

If a row matches a transaction that was already matched by a previous import, it gets an amber **DUP?** badge. It's still importable — sometimes you genuinely have two transactions for the same amount on the same day — but it's flagged so you can make a deliberate call rather than accidentally double-importing.

## Category fixes

A few bugs in the import preview's category column were fixed in the same release. The column is now always visible (previously it was hidden until you mapped a category field). The + Add button works for all rows, selected categories update immediately in the badge, and category assignments persist correctly when you adjust column mappings.
