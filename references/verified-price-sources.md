# Verified Price Sources

## 拓普报价表.xlsx

Confirmed by the user as the product price table.

Stored copy:

- `references/source-data/拓普报价表.xlsx`

Original provided path:

- `C:\Users\50428\OneDrive\桌面\拓普报价表.xlsx`

Workbook sheets:

- `产品成本统计`: control box products. Columns include `产品编码`, `版本`, `电源线`, `产品名称`, quantity tier columns `采购数量` / `采购单价`, `支持电压`, `频率选择`, `最大功率`, `备注`.
- `手柄价格`: remote/handle products. Columns include `型号`, `款式`, `电压`, `支持频率`, `价格`.
- `电源线价格`: power cord products. Columns include `产品编码`, `产品名称`, `是否带地线`, `采购数量`, `采购单价`, `备注`.

## Usage Notes

- Treat this workbook as verified price data, not merely an example.
- Do not quote a product that is absent from all three sheets unless the user supplies another verified catalog/price file.
- For `产品成本统计`, choose the price tier by quantity. The workbook currently has two visible purchase quantity/price pairs. If the requested quantity boundary is unclear because values use expressions such as `＜50` or `＜500`, ask before finalizing.
- When the same control box product has both `电容版` and `变压器版`, default to `电容版` unless the user or customer explicitly says `变压器版`.
- For products marked `选配电源线`, add power cord pricing only when the customer requests a power cord or the user confirms it should be included.
- For products marked `必须带电源线`, include or clarify the required power cord; do not assume the cord type unless the customer or user specifies it.
- Preserve sheet names and source file name in internal check notes for auditability.
