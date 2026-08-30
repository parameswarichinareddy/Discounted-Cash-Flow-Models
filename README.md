# European Large-Cap DCF Valuation Models

This repository contains three formula-driven discounted cash flow models covering **Airbus SE, Capgemini SE, and Schneider Electric SE**. Each workbook develops a company-specific operating forecast, calculates unlevered free cash flow, builds the weighted average cost of capital, and converts enterprise value into an implied equity value per share.

The models were prepared as portfolio projects using a common investment-banking-style structure while adapting the operating drivers and assumptions to each company’s business model.

## Repository Contents

| File | Company | Base year | Explicit forecast | Operating build |
|---|---|---|---|---|
| [Airbus_DCF_Model_Final.xlsx](models/Airbus_DCF_Model_Final.xlsx) | Airbus SE | FY2025A | FY2026E–FY2030E | Commercial Aircraft, Helicopters, Defence & Space, and intersegment eliminations |
| [Capgemini_DCF_Model_Fixed.xlsx](models/Capgemini_DCF_Model_Fixed.xlsx) | Capgemini SE | FY2025A | FY2026E–FY2030E | Strategy & Transformation, Applications & Technology, and Operations & Engineering |
| [SchneiderElectric_DCF_Model_Fixed.xlsx](models/SchneiderElectric_DCF_Model_Fixed.xlsx) | Schneider Electric SE | FY2025A | FY2026E–FY2030E | Energy Management and Industrial Automation |

Unless otherwise stated, financial amounts are presented in EUR millions and per-share values are presented in euros.

## Common Model Architecture

Each workbook contains the following worksheets:

| Worksheet | Purpose |
|---|---|
| **Executive Summary** | Key valuation outputs, reference share price, implied value per share, WACC, terminal-growth assumption, and navigation |
| **Model Guide** | Model conventions, tab-by-tab explanation, source notes, and company-specific modelling considerations |
| **Assumptions** | Centralized historical inputs, forecast drivers, capital-structure inputs, WACC assumptions, and terminal-value assumptions |
| **Revenue Build** | Bottom-up revenue forecast based on the company’s operating segments or service lines |
| **Income Statement & FCF** | Revenue, operating profit, taxes, NOPAT, D&A, capital expenditure, change in net working capital, and unlevered free cash flow |
| **WACC** | CAPM cost of equity, after-tax cost of debt, capital-structure weights, and weighted average cost of capital |
| **DCF Valuation** | Explicit-period present value, terminal value, enterprise-to-equity bridge, implied share value, and exit-multiple cross-check |
| **Sensitivity** | Implied share-price sensitivities across WACC/terminal-growth and WACC/exit-multiple ranges |
| **Error Checks** | Formula-driven integrity tests covering valuation mechanics, forecast continuity, errors, and circular references |

## Valuation Methodology

The models follow the same core process:

1. Forecast revenue from company-specific segment or service-line assumptions.
2. Apply operating-margin assumptions to derive the relevant EBIT or EBIT-proxy measure.
3. Calculate NOPAT by applying the forecast tax rate to operating profit.
4. Add depreciation and amortization, then deduct capital expenditure and the increase in net working capital to calculate unlevered free cash flow.
5. Calculate WACC using CAPM for the cost of equity and an after-tax cost of debt, weighted by the modelled capital structure.
6. Discount FY2026E–FY2030E unlevered free cash flows to the valuation date.
7. Calculate terminal value using the Gordon Growth method as the primary approach.
8. Add the present value of the explicit forecast and terminal value to derive enterprise value.
9. Deduct net debt—or add net cash—to derive equity value, then divide by diluted shares to calculate implied value per share.
10. Cross-check the result using an exit EV/EBITDA multiple and test the principal assumptions through sensitivity tables.

## Base-Case Valuation Snapshot

The figures below reproduce the workbook outputs and should be read only in the context of their stated assumptions.

| Company | Reference share price used | WACC | Terminal growth | Gordon Growth value/share | Exit-multiple cross-check |
|---|---:|---:|---:|---:|---:|
| Airbus | €214.10 | 7.56% | 2.0% | €193.75 | €240.17 |
| Capgemini | €102.51 | 7.82% | 1.5% | €189.57 | €139.82 |
| Schneider Electric | €236.55 | 7.60% | 2.0% | €205.92 | €251.18 |

The models state a valuation date of **4 August 2026**. Airbus uses the 4 August 2026 closing price. Capgemini’s reference price is derived from early-August 2026 market capitalization and diluted shares. Schneider Electric’s reference price is based on a 23 December 2025 closing price and therefore does not represent a 4 August 2026 market close.

## Airbus DCF Model

### Operating approach

Airbus revenue is forecast separately for Commercial Aircraft, Airbus Helicopters, and Defence & Space. A dedicated elimination/HQ line reconciles reported segment revenue to Group revenue and remains explicit in the forecast.

Adjusted EBIT is used as the operating-profit proxy. Forecast assumptions incorporate Airbus’s FY2026 Adjusted EBIT and free-cash-flow guidance and its FY2029 Adjusted EBIT target. The model uses reported D&A and capital expenditure run rates and calculates unlevered free cash flow before financing effects.

Airbus’s FY2025 net cash is included only in the enterprise-to-equity bridge. WACC uses gross interest-bearing financing liabilities rather than a negative debt weight, keeping the capital-structure calculation economically meaningful.

### Principal sources

- Airbus FY2025 Results and FY2025 Financial Statements, published 19 February 2026
- Airbus H1 2026 Results, published 29 July 2026
- Airbus Business Update, published 21 July 2026
- Airbus/Euronext Paris share-price history presented through Boursorama
- Banque de France TEC10 government-bond index
- NYU Stern/Damodaran aerospace and defence beta and implied equity-risk-premium datasets

Terminal growth, net-working-capital requirements, and the exit multiple remain analyst assumptions documented within the workbook.

## Capgemini DCF Model

### Operating approach

Capgemini revenue is forecast across Strategy & Transformation, Applications & Technology, and Operations & Engineering. FY2026 assumptions use management guidance as an anchor because the FY2025 base year was affected by the WNS acquisition and the associated increase in net debt.

The live calculation tabs use **statutory operating profit** as the EBIT base, then forecast operating margins, taxes, D&A, capital expenditure, and changes in net working capital to calculate unlevered free cash flow. WACC uses an industry unlevered beta that is relevered to Capgemini’s modelled post-acquisition capital structure.

### Documentation note

The Model Guide includes older narrative language referring to Capgemini’s adjusted Operating Margin*. The **Assumptions** and **Income Statement & FCF** worksheets are the live calculation source and explicitly use statutory operating profit. This distinction should be explained when presenting the model.

### Principal sources

- Capgemini FY2025 and H1 2025 results releases
- Capgemini FY2023 and FY2024 full-year results releases
- Capgemini FY2026 revenue-growth and margin guidance
- Stock Analysis market data used for market capitalization, shares, trading multiple, and supporting estimates

The effective tax rate, capital expenditure, D&A, working-capital requirement, risk-free rate, beta, cost of debt, and terminal-growth rate include analyst estimates or assumptions and should be refreshed before relying on the model for a current valuation.

## Schneider Electric DCF Model

### Operating approach

Schneider Electric revenue is forecast separately for Energy Management and Industrial Automation, reflecting their different growth profiles. Adjusted EBITA is used as the EBIT proxy, followed by forecast taxes, D&A, capital expenditure, and working-capital investment to calculate unlevered free cash flow.

The model incorporates the increase in net debt following the SEIPL minority buyout. Its WACC combines a CAPM-derived cost of equity with an after-tax cost of debt and market-value capital-structure weights.

### Principal sources

- Schneider Electric FY2025 Full Year Results release, published 26 February 2026
- Schneider Electric FY2023 Full Year Results release, published 15 February 2024
- Schneider Electric company filings for share data
- Schneider Electric’s December 2025 bond issuance for the cost-of-debt reference
- Simply Wall St beta data used in the workbook

The risk-free rate, equity-risk premium, D&A, working-capital requirement, terminal-growth rate, and exit multiple include analyst assumptions documented in the workbook.

## Modelling Conventions

- **Blue text:** hardcoded source data or analyst assumptions that may be changed for scenarios
- **Black text:** formulas calculated within a worksheet
- **Green text:** formulas linked to another worksheet
- **Yellow fill:** selected base-case or key output cells

Actual conventions should always be confirmed against the legend on each workbook’s **Model Guide** worksheet.

## How to Use the Models

1. Download the `.xlsx` files and open them in Microsoft Excel or a compatible spreadsheet application.
2. Begin with **Executive Summary**, then review **Model Guide** and **Assumptions** before interpreting the valuation.
3. Keep automatic calculation enabled so changes flow through the forecast, valuation, and sensitivity tables.
4. Change only clearly identified hardcoded input cells unless intentionally revising the model structure.
5. Preserve worksheet names because cross-sheet formulas depend on them.
6. Refresh market data, WACC inputs, company guidance, net debt, and share counts before using a model for a new valuation date.
7. Review both terminal-value approaches and the sensitivity tables rather than relying on a single point estimate.
8. Confirm that every item on **Error Checks** continues to display **PASS** and that the overall status remains satisfactory after making changes.

## Validation Status

At the time this README was prepared:

- All three workbooks passed a scan for common Excel errors, including `#REF!`, `#DIV/0!`, `#VALUE!`, `#NAME?`, `#N/A`, and `#NUM!`.
- Each workbook’s **Error Checks** worksheet reported passing tests for terminal growth versus WACC, declining discount factors, enterprise-value construction, the equity bridge, sensitivity-grid errors, continuous forecast years, and circular references.
- The Airbus workbook also reported an overall model status of **OK** and includes additional checks for source tie-outs, segment reconciliation, WACC construction, guidance alignment, and UFCF integrity.

## Limitations and Disclaimer

- DCF outputs are highly sensitive to WACC, terminal growth, operating margins, working-capital investment, capital expenditure, and terminal-value methodology.
- Terminal value represents approximately **76%–81% of enterprise value** in the base cases, so small changes in long-term assumptions can materially change the result.
- Reference share prices and external market inputs are historical snapshots and may no longer reflect current market conditions.
- Company guidance, reported financial data, and capital structures may change after the model dates.
- Secondary-source inputs should be independently verified against primary company disclosures before professional use.
- These models were prepared for portfolio, educational, and analytical purposes. They do not constitute investment advice, an offer, or a recommendation to buy or sell securities.
