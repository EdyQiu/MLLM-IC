# 🧪 MLLM-Image Corruption
**Evaluating and Analyzing the Robustness of Multimodal Large Language Models under Image Corruption**

This repository provides code and tools for reproducing the robustness benchmark of Multimodal LLMs (MLLMs) under various types of image corruption, as described in our paper.

## 📌 Highlights

- 🌪️ **Hierarchical Image Corruption Benchmark (MLLM-IC)**: Evaluates models across **severity**, **capability**, and **corruption** dimensions.
- 🧠 **11 SOTA MLLMs Evaluated**: Including LLaVA-1.5, DeepSeek-VL, Transcore-M, GPT-4o, Gemini 2.0, and more.
- 📊 **Comprehensive Visualizations**: Radar charts, heatmaps, and sensitivity maps to facilitate fine-grained analysis.

## 📂 Project Structure

- `benchmark/`: Benchmark execution and evaluation.
- `corruptions/`: Implementations of various image corruption types.
- `models/`: Wrappers for loading and querying each MLLM.
- `configs/`: YAML files specifying benchmark settings.
- `scripts/`: Quick-start bash scripts to run the evaluation.
- `results/`: Output tables and figures.

## 🖼️ Corruption Types

We simulate 40+ corruption types across:
- **Pixel-Level**: Noise, blur
- **Regional-Level**: Occlusion, weather
- **Global-Level**: Compression, geometric transformations

## 🧠 Capability Dimensions

To assess the robustness of Multimodal Large Language Models (MLLMs) under corrupted visual conditions, we adopt a **hierarchical capability framework** that decomposes model ability into **Perception** and **Reasoning**, each with mid- and low-level subskills.

### Perception Capabilities

| Mid-Level Capability         | Low-Level Skills                                                                 |
|-----------------------------|-----------------------------------------------------------------------------------|
| **Global Context Sensing**  | Image Topic, Image Quality, Image Emotion, Image Scene, Image Style, Scene Understanding |
| **Instance & Part Recognition** | Instance Identity, Attribute Recognition, Instance Interaction, Instance Attribute, Emotion Recognition, Action Recognition, Celebrity Recognition, Landmark Recognition |
| **Spatial Perception**      | Physical Relation, Instance Location, Instance Counting, Spatial Relation, Object Localization |


### Reasoning Capabilities

| Mid-Level Capability         | Low-Level Skills                                                                 |
|-----------------------------|-----------------------------------------------------------------------------------|
| **Knowledge Reasoning**     | Chart Understanding, Science Knowledge, Nature Relation, Structured Image-Text Understanding, Visual Mathematics, Function Reasoning, Physical Property Reasoning |
| **Logic Reasoning**         | Visual Reasoning, Visual Referring Expression, Social Relation, Identity Reasoning, Future Prediction, Attribute Comparison, Text Recognition, OCR |


### Why Capability Dimensions Matter

- ✅ **Fine-Grained Analysis**: Goes beyond aggregate accuracy to reveal how specific abilities degrade under corruption.
- ✅ **Model Differentiation**: For example, DeepSeek-VL excels at global context and logic reasoning, while Transcore-M is strong in part-level recognition.
- ✅ **Robustness Diagnosis**: Helps identify which model capabilities are more vulnerable to which types of image corruption (e.g., blur vs. occlusion).


## 🚀 Quick Start

```bash
# 1. Clone repo & install dependencies
git clone https://github.com/yourusername/MLLM-Robustness-Eval.git
cd MLLM-Robustness-Eval
pip install -r requirements.txt

# 2. Run benchmark on all models
bash scripts/run_all.sh
