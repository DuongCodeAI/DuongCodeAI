# Tiến Dương

**Trợ lý lái xe tiếng Việt chạy offline**: 5 dự án AI (RAG, computer vision, Transformer tự viết, fine-tune LLM, hệ thống ghép)

Hugging Face: [hgdkakhs](https://huggingface.co/hgdkakhs)

5 repo, 4 thành phần + 1 hệ thống ghép lại, chạy trên laptop không GPU (Ryzen 5 5625U). Số liệu dưới đây là số đã
chạy thật (04/10/2026), kể cả những chỗ chưa đạt.

**1. [vn-traffic-law-rag](https://github.com/DuongCodeAI/vn-traffic-law-rag): RAG tra luật giao thông**
Hỏi đáp NĐ 168/2024 + Luật 36/2024, trích dẫn tới Điểm/Khoản/Điều. BM25 + vector + RRF + rerank ONNX trên CPU.
Bộ eval tự làm 61 câu: recall@5 **0.86** (BM25 đơn thuần 0.74); riêng bảng từ đời thường → ngôn ngữ luật nâng
0.64 → 0.86, mở rộng tham chiếu nâng tỉ lệ "lấy đủ mức phạt + trừ điểm" 0.36 → 0.81. Đo ra embedding e5-small thua BM25 trên văn bản luật, và thêm dấu trước khi tìm
làm recall@5 tụt (0.83 → 0.72), nên cả hai không bật mặc định.

**2. [vn-dashcam-vision](https://github.com/DuongCodeAI/vn-dashcam-vision): nhận diện 52 loại biển báo**
2 tầng: YOLO11n 1 lớp tìm biển + CNN tự thiết kế (SignNet, 1.19M tham số) phân loại crop; tracker + bỏ phiếu nhiều
frame; suy luận tự viết bằng numpy + onnxruntime. mAP@0.5 **0.962** so với 0.801 của YOLO 52 lớp (lớp hiếm 0.950 so với
0.769), ~120 ms/ảnh trên 1 nhân CPU Colab. Sampler căn bậc 2 cho macro-F1 0.985. Int8 nhỏ hơn ~3 lần nhưng chưa nhanh hơn
trên CPU Colab. Chưa thử trên video xe máy.

**3. [vi-diacritics-transformer](https://github.com/DuongCodeAI/vi-diacritics-transformer): Transformer tự viết, thêm dấu tiếng Việt**
Attention, multi-head, positional encoding tự viết bằng PyTorch thuần; đặt bài toán thành gán nhãn từng ký tự
(30 lớp) nên không thể bịa chữ. Test Wikipedia word acc **0.948** (baseline bigram 0.854, ít lỗi hơn ~2.8 lần),
int8 7.2 MB chạy trong trình duyệt ([demo](https://duongcodeai.github.io/vi-diacritics-transformer/)). So với seq2seq
(nhiều tham số gấp đôi): seq2seq thua (0.919), đổi chữ ở 3.2% câu và chậm ~12 lần. Điểm yếu đã đo: tin nhắn chat chỉ 0.731.

**4. [vi-function-calling-slm](https://github.com/DuongCodeAI/vi-function-calling-slm): fine-tune LLM nhỏ gọi tool trong xe**
Qwen3-1.7B, QLoRA SFT + DPO, 17 tool, GGUF Q4_K_M chạy llama.cpp trên CPU. Dữ liệu tổng hợp 1.390 câu, nhãn sinh
bằng code (không để LLM gán nhãn). Model gốc chưa fine-tune: đúng tool 0.697 nhưng không bao giờ hỏi lại hay từ chối
lệnh không an toàn. Bản SFT + DPO đang train, số sẽ cập nhật ở README repo.

**5. [viet-copilot](https://github.com/DuongCodeAI/viet-copilot): ghép thành trợ lý lái xe**
Event bus bất đồng bộ (buồn ngủ > biển báo > lệnh giọng nói), STT PhoWhisper, TTS Piper, buồn ngủ bằng EAR/PERCLOS.
Cảnh báo biển báo không qua LLM: soát 52 mã biển × 2 loại xe, sửa từ 15/104 lên **88/104** cặp có cảnh báo đúng
mức phạt. Fine-tune STT với tiếng ồn ra kết quả **kém hơn** bản gốc (WER sạch 2.14% → 3.13%) nên giữ bản gốc.
STT small trên laptop: WER 2.8% (sạch) / 6.0% (ồn 10 dB) nhưng ~3 s/câu, nên lệnh giọng nói end-to-end mất khoảng
4–6 s, **chưa đạt** mục tiêu 1.5 s.

Cách làm chung: đo trước khi tối ưu, giữ cả kết quả âm (STT fine-tune kém hơn, seq2seq thua tagger, embedding thua
BM25), và soát lại số trên dữ liệu thật: so 3 size STT trên giọng tổng hợp suýt chọn sai model, đo lại trên giọng
người mới thấy chênh 4 lần.
