# Video-LLM UX Heuristic Evaluation Dataset & Code
This repository contains all supplementary materials for the study:

**“비디오 기반 LLM을 활용한 휴리스틱 평가와 인간 전문가의 상보적 강점 분석”**  
(A Comparative Analysis of Video-LLM Heuristic Evaluation and Human Expert Judgments)

This repository provides:
- Full task scenarios (A–J)
- Full Nielsen 10 Heuristics checklist used in the study
- Complete prompt used for Video-LLM evaluation
- Original evaluation video (downsampled for privacy)
- Five raw LLM JSON outputs + merged final output
- Python code for parsing, merging, deduplication, and statistical analysis
- All figures and tables reproduced via code
- Replication guide for researchers

All sensitive information has been removed or masked.

---

## ✨ 1. Repository Structure
<pre>
VideoLLM-UX-Eval/
├── input/
│ └── AndarVideo.mp4
│ └── checklist.pdf
├── output/
│ ├── sample_1.json
│ ├── sample_2.json
│ ├── sample_3.json
│ ├── sample_4.json
│ ├── sample_5.json
│ └── dyn_merged_breakdowns.json
│
├── prompts/
│ └── prompt.txt
│
├── src/
│ ├── VideoLLM.ipynb
│
├── LICENSE
└── README.md
</pre>
---

## 🔧 2. Requirements

Google Colab 에서 수행해야 하기 때문에 구글계정과 구글 드라이브에 input 파일을 올려야 한다. 

---

## ▶ 3. Running the Evaluation Pipeline

### Step 1: Generate 5 LLM Outputs
- Requires Google Gemini API key  
- 구글 드라이브 사용 권한 획득
- 구글 드라이브 파일 경로 수정   
- !pip install -q -U google-generativeai 실행
- api 실행 하면 순차적으로 json 파일 생성 (10분 이상 소요 ) 

### Step 2: Merge & Deduplicate
- output 파일 설정  "dyn_merged_breakdowns.json" 
- 파일 병합 실행  
---

## 📊 4. Data Description

### • Video
- 11.4 minutes, 1080p → downsampled version provided.
- All PII and payment information masked.

### • Human Expert Evaluation
- 5 UX experts (4–10y experience)
- Severity scale: 0–4
- Gold standard = consensus (≥3/5)

### • Video-LLM Evaluation
- Gemini 2.5 Pro
- 5-run self-consistency
- Output format: Strict JSON

---
 


