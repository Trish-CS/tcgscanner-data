TCGScanner Data

This repository contains the source of truth for card game data used in the **TCGScanner** app. It includes card metadata, sets, and derived minimal indexes for scanning and quick lookups in the app.

# Purpose
- Moving away from housing the entire card database within the application. Will work towards a DB and API.
- This repository will contain all trading card game information used, as well as provide the derived minimal indexes used within the mobile app.
- Allow safe updates and additions for new sets, games, or languages without breaking the app or future API.

# Structure
tcgscanner-data/
├── pokemon/
│   ├── sets.json                 ← canonical set data
│   ├── cards/                    ← full card data for each set
│   │   ├── sampleset1.json
│   │   └── sampleset2.json
│   └── derived/                  ← used by app
│       ├── cards_min.json
│       └── sets_min.json
├── mtg/                          ← future game support

# Notes
- Full Card Data (cards/*.json): Used for API/DB imports. Each card has a unique ID in the format 'setId-cardNumber'. The 'setId' prefix is used to link the card to its corresponding set in sets.json.
- Set Metadata (sets.json): Contains canonical set IDs, names, series, and codes.
- Derived Minimal Indexes (derived/*.json): Generated from the full data; used only in front-end apps for OCR TextRecognition scanning and comparison. Not imported to DB.
