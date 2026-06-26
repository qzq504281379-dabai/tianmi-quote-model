# Quotation Rules

## Integrity Rules

- Do not create a quotation line unless the product exists in the verified catalog and has a verified price.
- Do not fill unknown values with estimates, market prices, averages, or prices from similar products.
- Do not silently substitute another model. Ask for confirmation and record the confirmed choice.
- For products with both capacitor and transformer versions, default to `鐢靛鐗坄 unless the request explicitly says `鍙樺帇鍣ㄧ増`.
- Do not promise stock, delivery date, warranty, installation, freight, tax handling, or discount unless a verified rule or user confirmation supports it.
- Use blank, `寰呯‘璁, or a direct clarification question for unknown customer-facing fields.
- 单一产品标准配置：控制盒主体 + 一个遥控器/手柄。电源线默认不含，仅当客户或用户明确要求时加入。


- 表格末行需显示：各产品单价的合计（∑单价）+ 总价合计（∑合计）。
## Output Table

Create a customer-facing quotation table with these columns unless the user provides a template:

- 搴忓彿
- 浜у搧鍚嶇О
- 鍨嬪彿/瑙勬牸
- 鏁伴噺
- 鍗曚綅
- 鍗曚环
- 閲戦
- 甯佺
- 鏄惁鍚◣
- 浜ゆ湡/璐ㄤ繚/浠樻澶囨敞

Add subtotal, tax, freight, discount, and grand total only when supported by verified rules. If tax or freight is unknown, do not calculate a final all-in total.

## Internal Check Note

After the table, include a short internal note unless the user asks for customer-only wording:

- Source files and versions used.
- Items successfully matched.
- Items not quoted and why.
- User confirmations or assumptions.
- Fields still pending confirmation.

## Discount And Approval

Apply discounts only when the source file contains the discount rule or the user explicitly approves it in the conversation. If discount authority is unclear, produce the undiscounted quote and ask for approval before lowering price.

## Date And Validity

Use the quote date requested by the user. If none is provided, use the current date from the environment. Quote validity must come from a company rule or user confirmation; otherwise mark it as `寰呯‘璁.



