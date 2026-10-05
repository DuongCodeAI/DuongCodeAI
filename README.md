<div align="center">

<h1>Tiến Dương</h1>
<p><b>Software &amp; AI · Sinh viên năm 4</b></p>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1200&color=36BCF7&center=true&vCenter=true&width=640&lines=RAG+%C2%B7+Computer+Vision+%C2%B7+LLM+fine-tuning;AI+ch%E1%BA%A1y+offline+tr%C3%AAn+laptop+kh%C3%B4ng+GPU;2+app+doanh+nghi%E1%BB%87p+tr%C3%AAn+Google+Play" alt="typing"/>

<a href="mailto:khongtienduongcv@gmail.com"><img src="https://img.shields.io/badge/Email-khongtienduongcv%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
<a href="https://huggingface.co/hgdkakhs"><img src="https://img.shields.io/badge/Hugging%20Face-hgdkakhs-FFD21E?style=for-the-badge&logo=huggingface&logoColor=white"/></a>
<a href="https://duongcodeai.github.io/vi-diacritics-transformer/"><img src="https://img.shields.io/badge/Live%20demo-Th%C3%AAm%20d%E1%BA%A5u%20ti%E1%BA%BFng%20Vi%E1%BB%87t-2ECC71?style=for-the-badge&logo=googlechrome&logoColor=white"/></a>

</div>

## 👋 Về mình

- Mình là **Tiến Dương**, sinh viên năm 4.
- Đã làm các dự án thực tế về **phần mềm + AI**, trong đó có 2 app làm cho doanh nghiệp đã đăng lên **Google Play**:
  - 🛒 **ZikinMarket**
  - 🚗 **ZikinDriver**

  Cả hai app có tích hợp AI để gợi ý, đề xuất, cùng nhiều chức năng khác.
- Ngoài ra còn nhiều dự án sinh viên khác, gần nhất là bộ 5 dự án AI bên dưới.
- Mong muốn được học hỏi và nỗ lực hơn nữa trong hành trình sắp tới.
- 📫 Liên hệ: **[khongtienduongcv@gmail.com](mailto:khongtienduongcv@gmail.com)**

## 🛠️ Công nghệ

**AI**

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white"/>
<img src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black"/>
<img src="https://img.shields.io/badge/ONNX%20Runtime-005CED?style=for-the-badge&logo=onnx&logoColor=white"/>
<img src="https://img.shields.io/badge/llama.cpp-000000?style=for-the-badge"/>
<img src="https://img.shields.io/badge/YOLO-00B4D8?style=for-the-badge"/>
<img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white"/>
<img src="https://img.shields.io/badge/MediaPipe-0097A7?style=for-the-badge&logo=mediapipe&logoColor=white"/>
<img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white"/>
</p>

**Phần mềm**

<p>
<img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
<img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>
<img src="https://img.shields.io/badge/React%20Native-0A0A0A?style=for-the-badge&logo=react&logoColor=61DAFB"/>
<img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white"/>
</p>

## 🚀 Dự án nổi bật: Trợ lý lái xe tiếng Việt chạy offline

5 repo: 4 thành phần + 1 hệ thống ghép lại, chạy trên laptop không GPU. Mỗi repo có README ghi số đã chạy thật, kể cả chỗ chưa đạt.

| | Dự án | Làm gì | Điểm nhấn |
|---|---|---|---|
| ⚖️ | [**vn-traffic-law-rag**](https://github.com/DuongCodeAI/vn-traffic-law-rag) | RAG hỏi đáp luật giao thông, trích dẫn tới Điểm/Khoản/Điều | recall@5 **0.86** (BM25 0.74) |
| 🚦 | [**vn-dashcam-vision**](https://github.com/DuongCodeAI/vn-dashcam-vision) | Nhận diện 52 loại biển báo: YOLO11 + CNN tự thiết kế | mAP@0.5 **0.962**, ~80 ms/frame CPU |
| ✍️ | [**vi-diacritics-transformer**](https://github.com/DuongCodeAI/vi-diacritics-transformer) | Transformer tự viết từ đầu, thêm dấu tiếng Việt, chạy trên trình duyệt | word acc **0.948**, [demo](https://duongcodeai.github.io/vi-diacritics-transformer/) |
| 🧠 | [**vi-function-calling-slm**](https://github.com/DuongCodeAI/vi-function-calling-slm) | Fine-tune Qwen3-1.7B (QLoRA SFT + DPO) gọi 17 tool trong xe | args exact 0.52 → **0.91** |
| 🚗 | [**viet-copilot**](https://github.com/DuongCodeAI/viet-copilot) | Ghép tất cả: giọng nói, biển báo, buồn ngủ, tra luật | sửa cảnh báo biển báo 15 → **88/104** |

**Cách làm chung:** đo trước khi tối ưu, giữ cả kết quả âm (fine-tune STT kém hơn bản gốc, seq2seq thua tagger,
embedding thua BM25 trên văn bản luật) và ghi rõ chỗ chưa đạt (lệnh giọng nói end-to-end ~6 s trên CPU, mục tiêu 1.5 s).
Mỗi repo có CI (ruff + pytest), notebook Colab để train lại, model trên Hugging Face.

> *English: five repos that build an offline Vietnamese driving assistant on a CPU-only laptop: hybrid RAG over traffic law,
> two-stage traffic-sign recognition, a from-scratch Transformer for diacritics restoration, a QLoRA SFT + DPO fine-tuned
> Qwen3-1.7B for tool calling, and the system that ties them together. Every number in the READMEs comes from an actual run.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2C5364,50:203A43,100:0F2027&height=110&section=footer" width="100%"/>
