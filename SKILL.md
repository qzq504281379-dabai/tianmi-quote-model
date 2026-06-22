---
name: tianmi-quote-model
description: Create complete customer quotation tables for Tianmi company products from verified internal product catalogs, price tables, discount policies, and customer requirements. Use when preparing, checking, or revising Tianmi product quotes, quotation spreadsheets, customer-facing price sheets, or product configuration proposals; always avoid inventing products, prices, specifications, discounts, delivery terms, or unavailable data.
---

# 天米公司报价模型

## Core Rule

Only quote products, specifications, prices, discounts, and terms that are present in verified company source files supplied by the user or stored in the current workspace. If a customer request is ambiguous, incomplete, or not found in the company product/price data, stop and ask a concise clarification question before producing a customer-facing quotation.

Never infer missing prices from similar products. Never invent product models, accessories, service items, stock status, taxes, shipping fees, warranty terms, or delivery dates.

## Required Inputs

Before creating a quotation, locate or request these sources:

- Verified product catalog: product name/model/specification and sellable status.
- Verified price table: unit price, currency, tax inclusion, valid date or version.
- Quotation rules: discount approval, tax, freight, payment, warranty, and delivery rules.
- Customer requirement: requested product, quantity, configuration, destination, customer name, and requested quote date.

If any required input is missing, explain exactly which file or detail is needed and pause.

## Workflow

1. Read `references/verified-price-sources.md` to find confirmed Tianmi price files.
2. Read `references/data-sources.md` to understand the expected source files and columns.
3. Read `references/quotation-rules.md` for quotation guardrails and customer-facing output requirements.
4. Match each customer-requested item against the verified catalog by exact model first, then exact product name/specification. Treat fuzzy matches as candidates only; ask the user to choose when more than one candidate fits.
5. If a matched control box product has both `电容版` and `变压器版`, use `电容版` by default. Use `变压器版` only when the user or customer explicitly says so.
6. Confirm every matched item has a valid price in the price table for the requested currency/date/version.
7. Apply only documented quote rules. If the requested discount, tax handling, freight, or term is not documented, ask for confirmation.
8. Produce a complete customer quotation table with clear columns: item number, product name, model/specification, quantity, unit, unit price, amount, currency, tax status, delivery/warranty/payment notes, and validity period.
9. Include an internal check note listing source files used, unmatched requests, assumptions approved by the user, and any fields intentionally left blank.

## Ambiguity Handling

Ask before quoting when:

- The customer uses a short name, nickname, outdated name, or partial model number.
- Multiple catalog products could satisfy the request.
- Quantity, configuration, currency, tax status, or delivery destination affects price but is missing.
- The requested item is not in the catalog or is present in the catalog but missing from the price table.
- The customer asks for a package, bundle, accessory, service, or customization not documented in company files.

Use short questions such as: "客户说的 `X` 可能对应 A/B/C，请确认具体型号。" or "`X` 在产品目录中存在，但价格表没有对应价格；请提供最新价格表或确认是否不报价。"

## Script Use

Use `scripts/validate_quote_inputs.py` before finalizing a quote when CSV or XLSX source files are available. It checks requested items against product and price files and reports missing or ambiguous matches.

Example:

```bash
python scripts/validate_quote_inputs.py --catalog product_catalog.csv --prices price_table.csv --request quote_request.csv
python scripts/validate_quote_inputs.py --catalog references/source-data/拓普报价表.xlsx --prices references/source-data/拓普报价表.xlsx --request quote_request.xlsx
```

The script is a pre-check only. Still read the source files and apply the quotation rules before giving a customer-facing table.

## References

- `references/data-sources.md`: expected source file types, required columns, and version rules.
- `references/verified-price-sources.md`: confirmed Tianmi price workbook inventory and sheet meanings.
- `references/quotation-rules.md`: quote integrity rules, output structure, and approval checks.
- `references/customer-questions.md`: reusable clarification questions for common missing information.
