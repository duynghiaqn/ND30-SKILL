Thông số thể thức NĐ 30/2020/NĐ-CP
Tham chiếu Toàn bộ thông số pixel-perfect để sinh file .docx đúng chuẩn.

Khổ giấy và lề
Thông số	Giá trị	Đơn vị dxa
Khổ giấy	A4 (210 x 297 mm)	-
Lề trái	30 mm	~1701 dxa
Lề phải	20 mm	~1134 dxa
Lề trên	20 mm	~1134 dxa
Lề dưới	20 mm	~1134 dxa
Font mặc định	Times New Roman, Unicode	-
Header - Table 2 cột x 2 dòng ẩn viền
Đây là phần quan trọng nhất và hay bị sai nhất. Header PHẢI dùng Table ẩn viền, KHÔNG dùng Tab hay Space.
Cấu trúc Header
+---------------------------+------------------------------------------+
| DÒNG 1 - CỘT TRÁI (3500) | DÒNG 1 - CỘT PHẢI (5571)                |
| - Tên cơ quan chủ quản    | - QUỐC HIỆU (in hoa, đậm, cỡ 13)       |
| - TÊN CƠ QUAN BAN HÀNH   | - Tiêu ngữ (đậm, thường, cỡ 14)         |
|   + Gạch ngang 1/3        |   + Gạch ngang = chiều dài tiêu ngữ      |
+---------------------------+------------------------------------------+
| DÒNG 2 - CỘT TRÁI (3500) | DÒNG 2 - CỘT PHẢI (5571)                |
| - Số, Ký hiệu            | - Địa danh, ngày tháng (nghiêng, cỡ 14) |
| - V/v (Trích yếu, cỡ 12) |                                          |
+---------------------------+------------------------------------------+
Thông số chi tiết Header
Yếu tố	Vị trí	Cỡ chữ	Kiểu	Kẻ dưới
Quốc hiệu	Dòng 1, Phải (5571 dxa)	13	ĐẬM, IN HOA	Không
Tiêu ngữ	Dòng 1, Phải (dưới QH)	14	Đậm, Thường	Border Top, indent 1100 dxa
Cơ quan chủ quản	Dòng 1, Trái (3500 dxa)	13	Thường, IN HOA	Không
Cơ quan ban hành	Dòng 1, Trái (giữa)	13	ĐẬM, IN HOA	Border Top, indent 1350 dxa
Số, Ký hiệu	Dòng 2, Trái	13	Thường	Không
Địa danh, ngày tháng	Dòng 2, Phải	14	Nghiêng	Không
Trích yếu (V/v)	Dòng 2, Trái	12	Thường	Không
Body - Thông số khoảng cách
Thông số	Giá trị	Đơn vị twips
Khoảng cách trước đoạn	6pt	120 twips
Khoảng cách sau đoạn	6pt	120 twips
Giãn dòng	Chính xác 17pt	340 twips (LineRuleType.EXACT)
Lùi đầu dòng	1 - 1.27 cm	~720 twips
Cỡ chữ body	14 (hoặc 13)	-
Căn lề	Đều 2 bên (Justified)	-
Kỹ thuật gạch ngang - Border Top
TUYỆT ĐỐI KHÔNG dùng UnderlineType
Gạch ngang trong văn bản hành chính phải dùng Border Top trên một Paragraph trống. Không dùng UnderlineType, ImageRun, hay thẻ <v:line>.

Lý do: UnderlineType phụ thuộc vào nội dung text, khi in sẽ bị lệch. Border Top là đường viền cố định, không phụ thuộc text.

// Gạch dưới tên cơ quan (1/3 chiều rộng cột trái)
new Paragraph({
  spacing: { before: 20, after: 0 },
  border: {
    top: { style: BorderStyle.SINGLE, size: 2, color: "000000", space: 1 }
  },
  indent: { left: 1350, right: 1350 }
});

// Gạch dưới tiêu ngữ (bằng chiều dài chữ)
new Paragraph({
  spacing: { before: 20, after: 0 },
  border: {
    top: { style: BorderStyle.SINGLE, size: 2, color: "000000", space: 1 }
  },
  indent: { left: 1100, right: 1100 }
});