# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** Trần Xuân Nhật
- **Lớp:** HN-KS26-CNTT3
- **Link repository Pha2:** https://github.com/Vaaty367/HN-KS26-CNTT3_PromptAI_H02/blob/8ba2721abf3e94551cea8e3e53379611eb082ca4/bai_lam_pha2.md
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
[
  {
    "loai_ve": "VECH",
    "ngay_choi": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_tu": "nho",
    "ghi_chu": null
  },
  {
    "loai_ve": "VECN",
    "ngay_choi": "2027-01-03",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_tu": null,
    "ghi_chu": "Một người đang bó bột tay"
  },
  {
    "loai_ve": "VEVIP",
    "ngay_choi": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_tu": "lon",
    "ghi_chu": "một bạn đi xe lăn"
  }
]
```

**Link trò chuyện:** https://share.gemini.google/kcoqQ891JgQ6

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
1. Tiền vé người lớn:
8 × 250.000 = 2.000.000 đồng
2. Tiền vé trẻ em:
4 × (250.000 × 60%) + 2 × 0 = 4 × 150.000 + 0 = 600.000 đồng
3. Tiền vé:
2.000.000 + 600.000 = 2.600.000 đồng
4. Giảm giá đoàn:
2.600.000 × 10% = 260.000 đồng
5. Phụ thu:
6 × 40.000 = 240.000 đồng
6. Tổng tiền:
(2.600.000 - 260.000) + 240.000 = 2.340.000 + 240.000 = 2.580.000 đồng

[RESULT: 2.580.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/a6qTQPytiOcZ

### b) Kiểm tra kết quả AI

AI trả về kết quả chính xác

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "dong_khu_choi",
  "so_khach": 4,
  "so_khu_bi_dong": 2,
  "tom_tat": "Gia đình 4 người khiếu nại khu trượt nước chính và sóng nhân tạo đóng cửa không báo trước."
}
```

**Link trò chuyện:** https://share.gemini.google/WNEm9yhiWHuh

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| Đúng thông tin (50%) | 0/5 | - *"Vé chiều bên em 150k thôi ạ"*: Sai giá vé. Giá chuẩn của vé chiều (VECH) là 180.000 đồng/vé người lớn, không phải 150k.<br>

<br>- *"Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha."*: Sai chính sách đóng cửa vì thời tiết. Khi khách vào dưới 2 giờ (như trường hợp 1 tiếng của khách), công ty tặng 1 vé cùng loại sử dụng trong 30 ngày chứ không hoàn tiền mặt. | - *"Dạ, giá vé buổi chiều (VECH) dành cho người lớn là 180.000 đồng/vé ạ."*<br>

<br>- *"Nếu trời mưa to khiến công viên đóng cửa khi quý khách mới vào được dưới 2 giờ (như trường hợp 1 tiếng), bên em sẽ tặng 1 vé cùng loại có thời hạn sử dụng trong 30 ngày chứ không hoàn tiền mặt ạ."* |
| Đầy đủ (30%) | 1.5/3 | - Trả lời được 2 câu hỏi của khách (giá vé và chính sách khi mưa đóng cửa sau 1 tiếng) nhưng thông tin sai lệch.<br>

<br>- Thiếu lời mời khách cung cấp ngày đi chơi và số lượng vé để đặt vé. | - *"Để em hỗ trợ đặt vé nhanh chóng cho mình, anh/chị cho em xin ngày dự kiến đi chơi và số lượng vé mình cần nhé ạ."* |
| Giọng điệu (20%) | 0.5/2 | - *"Hello chị!"*, *"mát rượi luôn"*, *"nha"*, *"Cần gì ới em nhé!"*: Xưng hô thiếu chuẩn mực (chưa rõ giới tính/xưng hô khách hàng) và dùng nhiều từ ngữ suồng sã, thiếu chuyên nghiệp trong tư vấn dịch vụ. | - *"Dạ em chào anh/chị ạ. Thời tiết buổi chiều thường dễ chịu hơn, em xin gửi anh/chị thông tin chi tiết để mình tham khảo ạ. Nếu cần hỗ trợ thêm thông tin nào, anh/chị cứ nhắn cho em nhé ạ."* |
| **Tổng điểm** | **2/10** |  |  |
```

**Link trò chuyện:** https://share.gemini.google/hhrpJl4347RC
