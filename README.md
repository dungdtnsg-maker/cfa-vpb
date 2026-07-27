# VPBank CFA iOS v1.3.3

Source iOS chạy offline cho bộ VPBank CFA All-in-one:

- UPPER HHB.
- Houseowner.
- TAX+.
- Máy tính lãi vay.

Logic UPPER giữ đúng file Excel V5.4:

- NORMAL hiển thị 8 ô dư nợ doanh nghiệp.
- GOOD/BAD hiển thị 4 ô riêng và không gắn nhãn “Trung Dài hạn”.
- BAD vượt 30% doanh thu VAT năm sẽ không thỏa.
- Không sửa công thức workbook gốc.

## Build IPA miễn phí trên GitHub

Nên dùng repository **Private** vì source chứa công thức nghiệp vụ.

1. Upload toàn bộ nội dung thư mục source này lên repository GitHub.
2. Mở `Actions` → `Build IPA miễn phí` → `Run workflow`.
3. Tải artifact `VPBank-CFA-iOS-IPA`.
4. Giải nén để lấy `VPBank_CFA_v1.3.3-iOS-unsigned.ipa`.

IPA tạo ra chưa ký. Dùng Sideloadly hoặc AltStore để ký bằng Apple ID và cài
vào iPhone. Apple ID miễn phí thường cần gia hạn sau 7 ngày.

## Build trên macOS

```bash
brew install xcodegen
bash scripts/build_unsigned_ipa.sh dist
```

## Kiểm thử

```bash
npm ci --ignore-scripts
npm test
```
