---
title: "OtterFin is now open source"
date: 2025-03-01
draft: false
---

OtterFin is now open source under the [AGPLv3 license](https://www.gnu.org/licenses/agpl-3.0.html).

It started as a tool to manage our own household finances. We wanted something self-hosted, multi-currency, and built for families rather than individuals. After running it ourselves for over a year, we decided to open it up.

## What's included

- **Account-based ledger:** single-entry, with category splits and virtual accounts
- **Multi-currency support:** per-account base currency, transaction-level rate overrides, and a global exchange rate store
- **Family accounts:** household as the top-level entity, with Owner/Member/Viewer roles
- **Smart import:** CSV, QIF/QFX, OFX, and Google Sheets, with a full preview before committing
- **Built-in reporting:** net worth, income vs. expenses, spending by category

## Getting started

Run it with Docker:

```bash
git clone https://github.com/OtterFin-ai/otterfin.git
cd otterfin
cp .env.example .env
docker compose up -d
```

Then open [http://localhost:3000](http://localhost:3000).

## What's next

The project is still in active development. Budget tracking and improved reporting are coming in the next few weeks — we'll post updates here as they ship.

If you run into anything or have ideas, open an issue on [GitHub](https://github.com/OtterFin-ai/otterfin) or join the [Discord](https://discord.gg/JuQNMMqpTD).
