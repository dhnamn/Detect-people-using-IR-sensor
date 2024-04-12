# Detect-people-using-IR-sensor
1, Giới thiệu
- Sử dụng bộ thu phát hồng ngoại phát hiện người qua cửa

2, Linh kiện sử dụng
- Cặp thu phát hồng ngoại
- IC LM311
- Vi điều khiển STM32F103C8T6

3, Nguyên lý
- LED phát hồng ngoại luôn luôn phát ra sóng ánh sáng có bước sóng hồng ngoại, LED
thu bình thường có nội trở rất lớn (khoảng vài trăm Ω) , khi led thu nhận tia hồng ngoại 
chiếu vào đủ lớn thì nội trở của nó giảm xuống (khoảng vài chục Ω).
- Ban đầu, ta sẽ điều chỉnh biến trở để cho đèn phát quang tắt. Vặn biến trở để V+ lớn hơn
V- làm cho Vout > 0 đèn LED sẽ tắt.
- Khi có người đi qua, đèn LED thu sẽ không nhận được tín hiệu sóng hồng ngoại làm cho 
trở RD1 bé đi chỉ còn có vài chục Ω. Khi V- lớn hơn V+ làm cho Vout < 0. Từ đó làm cho 
LED phát quang phát sáng
- Khi đó ta sẽ xử lý tín hiệu điện qua chân Vout thông qua vi điều khiển 
STM32F103C8T6
