# OXR/docs/benchmark.md

## 1. Overview

OXR-1.0 ranks first in the displayed comparison snapshots: **87.84 on olmOCR-bench, 97.18 on OmniDocBench, and 87.76 on DocParsingBench**. It also leads the 21-model speed comparison, reaching **557.77 native tokens/s** and **0.990373 pages/s**.

Accuracy snapshot: 5 October 2026. Rankings apply to the displayed models and recorded evaluation protocols.

## 2. Accuracy Benchmarks

Tables follow the model order in Figure 1. ↑ Higher is better; ↓ lower is better; NR means not reported. Overall scores retain their original definitions; equal scores share a rank.

![](https://raw.githubusercontent.com/SoMarkAI/image_bed/main/OXR_README/assets/three-benchmark-leaderboards-olm-main.png)

*Figure 1. Overall scores on olmOCR-bench, OmniDocBench, and DocParsingBench. Panels use separate, truncated axes.*

### 2.1 olmOCR-bench

Official macro score using olmocr 0.4.27: 8,413 rules, eight categories, and 1,403 pages.

*Table 1. olmOCR-bench overall and all eight component scores (%).*

| **Rank** | **Model** | **Overall ↑** | **ArXiv Math ↑** | **Baseline ↑** | **Headers / Footers ↑** | **Long Tiny Text ↑** | **Multi Column ↑** | **Old Scans ↑** | **Old Scans Math ↑** | **Tables ↑** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | **OXR-1.0** | **87.84** | **92.76** | **97.35** | **94.34** | **90.95** | **85.18** | **59.32** | **89.74** | **93.05** |
| 2 | Infinity-Parser2-Pro | 87.60 | 88.10 | 99.90 | 95.80 | 92.50 | 83.70 | 58.20 | 91.30 | 91.20 |
| 3 | Chandra-OCR-2 | 85.80 | 86.90 | 99.90 | 91.40 | 93.70 | 82.10 | 51.10 | 89.10 | 92.10 |
| 4 | dots.mocr | 83.90 | 85.90 | 99.70 | 94.00 | 81.60 | 85.30 | 48.20 | 85.50 | 90.70 |
| 5 | jina-ocr-v1 | 83.40 | 86.10 | 99.90 | 88.70 | 93.20 | 85.50 | 42.60 | 82.30 | 88.80 |
| 6 | Surya-OCR-2 | 83.30 | 88.30 | 99.70 | 92.50 | 93.70 | 82.40 | 41.80 | 81.40 | 86.60 |
| 7 | LightOnOCR-2-1B\* | 83.20 | 89.60 | 99.60 | 19.70 | 91.40 | 84.80 | 42.20 | 85.60 | 89.00 |
| 8 | Chandra | 83.10 | 82.20 | 99.90 | 90.80 | 92.30 | 81.20 | 50.40 | 80.30 | 88.00 |
| 9 | Infinity-Parser-7B | 82.50 | 84.40 | 99.80 | 88.70 | 86.40 | 84.20 | 47.90 | 83.80 | 85.00 |
| 10 | Falcon-OCR\* | 80.30 | 80.50 | 99.50 | 94.00 | 78.50 | 87.10 | 43.50 | 69.20 | 90.30 |
| 11 | Qianfan-OCR | 79.80 | 80.10 | 99.60 | 92.20 | 89.10 | 80.40 | 42.00 | 73.10 | 81.60 |
| 12 | dots.ocr | 79.10 | 82.10 | 99.50 | 94.10 | 81.20 | 82.40 | 40.90 | 64.20 | 88.30 |
| 13 | DeepSeek-OCR-2 | 76.30 | 82.00 | NR | NR | 90.70 | 79.00 | 33.80 | 72.00 | 77.40 |
| 14 | LightOnOCR-1B-1025\* | 76.10 | 81.40 | 99.60 | 35.50 | 88.70 | 80.00 | 35.20 | 71.60 | 76.40 |
| 15 | DeepSeek-OCR | 75.70 | 77.20 | 99.80 | 96.10 | 79.40 | 66.40 | 33.30 | 73.60 | 80.20 |
| 16 | MinerU2.5-2509-1.2B | 75.20 | 76.60 | 93.70 | 96.60 | 83.50 | 78.20 | 33.70 | 54.60 | 84.90 |
| 16 | GLM-OCR\* | 75.20 | 80.70 | 98.80 | 95.80 | 86.90 | 76.70 | 37.60 | 68.30 | 77.60 |

Peer-model scores are sourced from published papers, model cards, and the [olmOCR-bench leaderboard](https://huggingface.co/datasets/allenai/olmOCR-bench).

### 2.2 OmniDocBench

Overall and component results on 1,651 pages. Xiaomi-OCR-0 uses the authors’ released Mix-RL results; other peer-model scores are sourced from the [v1.6_full table in opendatalab/OmniDocBench’s README](https://github.com/opendatalab/OmniDocBench/blob/f133a71e9e91c3621c7ce8994200a7b394a06eb3/README.md#end-to-end-evaluation), at commit [f133a71e9e91c3621c7ce8994200a7b394a06eb3](https://github.com/opendatalab/OmniDocBench/commit/f133a71e9e91c3621c7ce8994200a7b394a06eb3).

*Table 2. OmniDocBench results. Edit distances: four decimals; percentage scores: two decimals.*

| **Rank** | **Model** | **Overall ↑** | **Text Edit ↓** | **Formula CDM ↑** | **Table TEDS ↑** | **Table TEDS-S ↑** | **Reading Order Edit ↓** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | **OXR-1.0** | **97.18** | **0.0251** | **97.44** | **96.62** | **98.44** | **0.1214** |
| 2 | TeleOCR | 96.91 | 0.0267 | 96.59 | 96.82 | 98.18 | 0.1184 |
| 3 | Xiaomi-OCR-0 | 96.83 | 0.0313 | 98.50 | 95.11 | 97.19 | 0.1221 |
| 4 | OvisOCR2 | 96.47 | 0.0265 | 97.49 | 94.58 | 96.98 | 0.1120 |
| 5 | PaddleOCR-VL-1.6 | 96.34 | 0.0326 | 97.53 | 94.76 | 97.10 | 0.1278 |
| 6 | MinerU2.5-Pro | 95.75 | 0.0360 | 97.45 | 93.42 | 95.92 | 0.1200 |
| 7 | GLM-OCR | 95.22 | 0.0440 | 97.18 | 92.83 | 95.39 | 0.1330 |
| 8 | PaddleOCR-VL-1.5 | 94.93 | 0.0380 | 96.89 | 91.67 | 94.37 | 0.1300 |
| 9 | PaddleOCR-VL | 94.18 | 0.0400 | 95.91 | 90.65 | 93.74 | 0.1350 |
| 10 | Unlimited-OCR | 94.00 | 0.0394 | 95.72 | 90.21 | 93.36 | 0.1281 |
| 11 | Qianfan-OCR | 93.90 | 0.0400 | 95.08 | 90.53 | 93.31 | 0.1300 |
| 12 | Youtu-Parsing | 93.74 | 0.0440 | 93.63 | 92.02 | 95.00 | 0.1160 |
| 13 | Ovis2.6-30B-A3B | 93.70 | 0.0350 | 95.17 | 89.44 | 92.40 | 0.1350 |
| 14 | Logics-Parsing-v2 | 93.33 | 0.0410 | 95.65 | 88.42 | 91.98 | 0.1370 |
| 15 | ABot-OCR | 93.30 | 0.0370 | 94.86 | 88.69 | 91.87 | 0.1370 |
| 16 | FireRed-OCR | 93.26 | 0.0370 | 95.44 | 88.04 | 91.06 | 0.1310 |
| 17 | MinerU-2.5 | 93.04 | 0.0450 | 95.77 | 87.88 | 91.47 | 0.1300 |
| 18 | Gemini 3 Pro | 92.91 | 0.0640 | 95.99 | 89.15 | 92.96 | 0.1650 |
| 19 | Gemini 3 Flash | 92.62 | 0.0660 | 95.16 | 89.29 | 93.51 | 0.1720 |
| 20 | dots.ocr | 90.77 | 0.0480 | 89.95 | 87.18 | 90.58 | 0.1380 |
| 21 | OpenDoc-0.1B | 90.67 | 0.0490 | 93.02 | 83.88 | 87.45 | 0.1400 |
| 22 | DeepSeek-OCR-2 | 90.25 | 0.0500 | 91.84 | 83.89 | 87.75 | 0.1440 |
| 23 | HunyuanOCR | 89.95 | 0.0880 | 87.68 | 91.01 | 93.23 | 0.1710 |

### 2.3 DocParsingBench

OXR-1.0 ranks first in Overall, Text, Formula, and Table among the 17 compared systems.

*Table 3. DocParsingBench overall and component scores (0–100).*

| **Rank** | **Model** | **Overall ↑** | **Text ↑** | **Formula ↑** | **Table ↑** |
| --- | --- | --- | --- | --- | --- |
| **1** | **OXR-1.0** | **87.76** | **90.60** | **85.76** | **80.04** |
| 2 | PaddleOCR-VL-1.6 | 85.17 | 88.86 | 75.59 | 74.95 |
| 3 | jina-ocr-v1 | 84.46 | 89.05 | 78.08 | 75.03 |
| 4 | FireRed-OCR | 84.05 | 88.02 | 74.77 | 69.30 |
| 5 | TeleOCR | 83.13 | 86.42 | 76.19 | 76.77 |
| 6 | dots.mocr | 83.06 | 86.73 | 81.99 | 75.18 |
| 7 | MinerU2.5-Pro | 82.78 | 86.22 | 82.06 | 76.73 |
| 8 | Infinity-Parser2-Pro | 82.63 | 86.43 | 78.52 | 72.48 |
| 9 | OvisOCR2 | 82.26 | 85.76 | 73.48 | 74.20 |
| 10 | Chandra OCR 2 | 82.20 | 86.24 | 81.82 | 77.69 |
| 11 | Qianfan-OCR | 81.45 | 85.30 | 69.36 | 69.54 |
| 12 | ABot-OCR | 80.42 | 84.98 | 71.35 | 60.92 |
| 13 | GLM-OCR | 80.34 | 83.72 | 75.94 | 71.85 |
| 14 | Youtu-Parsing | 76.25 | 81.34 | 73.17 | 72.48 |
| 15 | HunyuanOCR 1.5 | 75.35 | 78.73 | 74.62 | 63.65 |
| 16 | LightOnOCR-2-1B | 71.88 | 76.44 | 73.80 | 66.34 |
| 17 | Surya-OCR-2 | 71.75 | 75.44 | 76.19 | 66.95 |

OXR scores are averaged over three evaluation rounds. Each round attempts 1,400 pages; the fixed 58-page exclusion set leaves 1,342 pages for scoring.

## 3. Inference Performance

### 3.1 Hardware and measurement protocol

All speed tests use one NVIDIA RTX PRO 6000 Blackwell GPU (96 GB), a 24-CPU quota, and 96 GiB RAM with no swap. OXR uses vLLM 0.25.1. Serial recognition excludes the model reading-order stage; the end-to-end pipeline includes it.

The speed workload is a frozen, stratified, approximately uniform 100-page subset of the 1,651-page OmniDocBench source set. The same 100 unique pages are reused across models. The speed subset is separate from the full accuracy evaluations.

Frozen 100-page workload: the JSON attachment lists the dataset and all 100 filenames used for speed testing.

[frozen-100-pages.json](./frozen-100-pages.json)

Serial decode tok/s excludes each request’s first token and input prefill time, and uses native decode time. Native tokens vary by tokenizer. End-to-end pages/s is 100 divided by total wall time.

![](https://raw.githubusercontent.com/SoMarkAI/image_bed/main/OXR_README/assets/recognition-speed.png)

*Figure 2. Serial recognition decoding and end-to-end throughput; the same 21 models, ranked independently.*

### 3.2 Serial recognition decoding speed

OXR’s serial decode throughput is **8.0% higher** than the next-highest result, PaddleOCR-VL-1.6.

*Table 4. Serial recognition decoding speed, ranked from fastest to slowest; corresponds to Figure 2’s left panel.*

| **Rank** | **Model** | **Serial decode (tok/s) ↑** |
| --- | --- | --- |
| **1** | **OXR-1.0** | **557.77** |
| 2 | PaddleOCR-VL-1.6 | 516.39 |
| 3 | OvisOCR2 | 498.23 |
| 4 | MinerU2.5-Pro | 475.96 |
| 5 | HunyuanOCR | 473.50 |
| 6 | LightOnOCR-2-1B | 408.27 |
| 7 | DeepSeek-OCR-2 | 400.18 |
| 8 | TeleOCR | 352.66 |
| 9 | GLM-OCR | 333.33 |
| 10 | FireRed-OCR | 244.51 |
| 11 | ABot-OCR | 244.32 |
| 12 | Surya-OCR-2 | 240.51 |
| 13 | dots.mocr | 235.71 |
| 14 | jina-ocr-v1 | 225.73 |
| 15 | OpenDoc-0.1B | 189.58 |
| 16 | Chandra-OCR-2 | 134.25 |
| 17 | Youtu-Parsing | 109.40 |
| 18 | Infinity-Parser-7B | 89.98 |
| 19 | Logics-Parsing-v2 | 32.73 |
| 20 | Qianfan-OCR | 26.91 |
| 21 | Infinity-Parser2-Pro | 10.13 |

### 3.3 End-to-end page throughput

OXR averages **100.972 seconds per 100 pages** across two rounds, with **33.5% higher throughput** than the next-highest result, OvisOCR2.

*Table 5. End-to-end throughput and 100-page wall time, ranked from fastest to slowest; corresponds to Figure 2’s right panel.*

| **Rank** | **Model** | **Pages/s ↑** | **100 pages (s) ↓** |
| --- | --- | --- | --- |
| **1** | **OXR-1.0** | **0.990373** | **100.972** |
| 2 | OvisOCR2 | 0.741960 | 134.778 |
| 3 | PaddleOCR-VL-1.6 | 0.690952 | 144.728 |
| 4 | DeepSeek-OCR-2 | 0.620544 | 161.149 |
| 5 | LightOnOCR-2-1B | 0.582376 | 171.710 |
| 6 | HunyuanOCR | 0.570617 | 175.249 |
| 7 | ABot-OCR | 0.460113 | 217.338 |
| 8 | MinerU2.5-Pro | 0.392674 | 254.664 |
| 9 | FireRed-OCR | 0.332920 | 300.373 |
| 10 | GLM-OCR | 0.324711 | 307.966 |
| 11 | Qianfan-OCR | 0.264628 | 377.889 |
| 12 | jina-ocr-v1 | 0.173598 | 576.044 |
| 13 | Surya-OCR-2 | 0.146384 | 683.136 |
| 14 | TeleOCR | 0.135909 | 735.789 |
| 15 | Infinity-Parser-7B | 0.134736 | 742.192 |
| 16 | dots.mocr | 0.126064 | 793.250 |
| 17 | Chandra-OCR-2 | 0.064192 | 1557.821 |
| 18 | OpenDoc-0.1B | 0.027713 | 3608.370 |
| 19 | Youtu-Parsing | 0.023726 | 4214.749 |
| 20 | Logics-Parsing-v2 | 0.019561 | 5112.234 |
| 21 | Infinity-Parser2-Pro | 0.015530 | 6439.086 |

OXR repeats the same 100 unique pages twice. Its reported 100-page time is the mean of the two rounds (100.972 s); throughput is 200 completed page attempts divided by their combined wall time (201.944 s). These are 200 timed observations of the same 100 pages.
