# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600259
**Name:** Phạm Hải Đăng
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Tối ưu và chính xác. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Kết quả sai, Nuclear Reactor không phải sản phẩm tiêu dùng. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả lời sai vì dữ liệu đầu vào (Garbage Data) bị nhiễm bẩn nghiêm trọng. Có các vấn đề sau:
1. **Outliers & Bad Data**: "Nuclear Reactor" được gắn nhãn "electronics" với giá trên trời ($999999). Agent chỉ đơn thuần tìm giá cao nhất trong category "Electronics" nên bị đánh lừa.
2. **Duplicate IDs**: Có 2 record cùng ID=1 (Laptop và Banana), gây thiếu nhất quán.
3. **Wrong Data Types**: "Broken Chair" có giá là "ten dollars" (string), khiến các phép toán so sánh bị lỗi hoặc bỏ qua.
4. **Null Values & Missing Category**: Có "Ghost Item" thiếu ID và Category, khiến Agent không thể truy xuất thông tin chính xác.
5. **Data Quality**: Chất lượng dữ liệu thấp khiến Agent đưa ra quyết định sai lầm, gây tổn thất cho người dùng.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Đồng ý. Dù prompt có hay đến đâu nhưng nếu dữ liệu "Kiến thức" (Knowledge Base) bị sai, Agent sẽ đưa ra các câu trả lời "Ảo giác" (Hallucinations) một cách rất tự tin. Data Chất lượng là nền móng của mọi hệ thống AI Agent tin cậy.
