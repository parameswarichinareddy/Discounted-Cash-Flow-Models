# Discounted Cash Flow Models

A portfolio of investment-banking-style Discounted Cash Flow (DCF) valuation models for Airbus, Capgemini, and Schneider Electric.

## Models

- `models/Airbus_DCF_Model_Final.xlsx` — Airbus DCF valuation
- `models/Capgemini_DCF_Model_Fixed.xlsx` — Capgemini DCF valuation
- `models/SchneiderElectric_DCF_Model_Fixed.xlsx` — Schneider Electric DCF valuation

## What the models demonstrate

- Bottom-up revenue forecasting
- Three-statement / free-cash-flow forecasting
- WACC and CAPM
- Unlevered free cash flow valuation
- Gordon Growth terminal value
- Exit EV/EBITDA cross-check
- Enterprise value to equity value bridge
- WACC / terminal-growth sensitivity analysis
- Model error checks and presentation-ready outputs

## Repository structure

```text
.
├── models/
│   ├── Airbus_DCF_Model_Final.xlsx
│   ├── Capgemini_DCF_Model_Fixed.xlsx
│   └── SchneiderElectric_DCF_Model_Fixed.xlsx
├── .github/
│   └── workflows/
│       └── validate-models.yml
└── README.md
```

## Automated quality control

GitHub Actions validates that the three workbooks are present, readable as Excel files, contain the expected core DCF worksheets, and do not expose obvious Excel error literals in stored cells.

## Purpose

This repository is intended as a financial-modelling and investment-banking portfolio demonstrating practical DCF construction, valuation methodology, documentation, and model-quality control.

> **Disclaimer:** These models are for educational and portfolio purposes only and are not investment advice. Market data, assumptions, and valuation outputs are time-sensitive and should be independently verified before real-world use.
