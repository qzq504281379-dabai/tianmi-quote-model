# Data Sources

Use verified company files only. Prefer files in the user's current workspace or files explicitly provided in the conversation. Treat screenshots, copied text, and old quote files as secondary evidence unless the user confirms they are current.

## Product Catalog

Expected columns, with equivalent Chinese names acceptable:

- `product_id` or `产品编号`
- `product_name` or `产品名称`
- `model` or `型号`
- `specification` or `规格`
- `unit` or `单位`
- `sellable_status` or `可销售状态`
- `notes` or `备注`

Only quote rows marked sellable/active/current. If status is missing, ask whether the item can be quoted.

## Price Table

Expected columns, with equivalent Chinese names acceptable:

- `product_id` or `产品编号`
- `product_name` or `产品名称`
- `model` or `型号`
- `unit_price` or `单价`
- `currency` or `币种`
- `tax_included` or `是否含税`
- `valid_from` or `生效日期`
- `valid_to` or `失效日期`
- `price_version` or `价格版本`

Quote only prices valid for the requested quote date. If several prices are valid, ask which version to use unless a company rule resolves the conflict.

## Customer Request

Expected columns:

- `requested_item` or `客户需求/产品`
- `model` or `型号`
- `quantity` or `数量`
- `configuration` or `配置`
- `destination` or `收货地`
- `customer_name` or `客户名称`

Quantity must be numeric and positive. If quantity is missing, ask before calculating amount.

## Source Priority

1. Latest official company catalog and price table.
2. Current sales/finance-approved quotation rule file.
3. User-confirmed updates in the conversation.
4. Historical quote files, only as formatting examples unless explicitly confirmed as current data.
