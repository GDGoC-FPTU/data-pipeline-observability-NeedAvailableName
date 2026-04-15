[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573997&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** monkeydangluffy@gmail.com

**Name:** Phạm Hải Đăng

---

## Mo ta

Bài lab này thực hiện xây dựng một pipeline ETL (Extract, Transform, Load) tự động để xử lý dữ liệu sản phẩm từ file JSON sang CSV. Pipeline bao gồm các bước kiểm tra chất lượng dữ liệu (Validation) để loại bỏ các record lỗi và chuẩn hóa dữ liệu (Transformation) trước khi lưu trữ. Ngoài ra, bài lab còn thực hiện thí nghiệm Stress Test với AI Agent để chứng minh tầm quan trọng của chất lượng dữ liệu đối với hiệu suất của Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Để so sánh tác động của dữ liệu:
# 1. Chạy pipeline để tạo processed_data.csv từ raw_data.json
# 2. Chạy simulation để xem kết quả giữa Clean Data và Garbage Data
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- **ETL Pipeline**: Đã xử lý 5 records từ `raw_data.json`, trong đó:
    - 3 records hợp lệ được lưu vào `processed_data.csv`.
    - 2 records bị loại bỏ (1 record giá <= 0, 1 record thiếu category).
- **Observability**: AI Agent hoạt động tốt với dữ liệu sạch (Accuracy 10/10) nhưng đưa ra câu trả lời sai lầm với dữ liệu rác (Accuracy 2/10), khẳng định vai trò của Data Quality.
