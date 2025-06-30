<<<<<<< HEAD
# trt-llm-surgery
Automatic Precision Surgery for Long-Context LLM Deployment using TensorRT
=======

# TensorRT-LLM Surgery: Automatic Precision Surgery for Long-Context LLM Deployment

## 🌟 Why This Project Matters

### 🔥 High Relevance
Long-sequence inference (e.g., 32K+ tokens) has emerged as a key performance bottleneck in LLM deployment. Recent GTC sessions and research from NVIDIA highlight the growing industry focus on this challenge, including:
- [“Accelerate Super Long‑Context LLM Inference” (GTC 2025)](https://www.nvidia.com/en-us/on-demand/session/gtc25-s72568/)
- [“Scaling to Millions of Tokens with Efficient Long‑Context LLM Training” (NVIDIA Developer Blog)](https://developer.nvidia.com/blog/scaling-to-millions-of-tokens-with-efficient-long-context-llm-training/)

### 🧠 Addressing Real Deployment Challenges
Handling dynamic batches, flexible input shapes, memory bottlenecks, and precision tradeoffs are common challenges in LLM inference. This project integrates those techniques into a practical workflow for optimizing long-sequence performance.

### 🎯 Real-World Impact
This tool automatically identifies layer-level bottlenecks and applies precision surgery to balance latency, accuracy, and memory — simulating the kinds of tradeoffs made in production deployments.

---

## 🧠 Project Goals

Build a profiling tool and optimization pipeline that:

- Analyzes long-sequence LLM (e.g., Mistral-7B, LLaMA-3-8B) during TensorRT inference
- Automatically identifies attention-heavy or memory-bottleneck layers
- Applies selective precision overrides (FP16/INT8/FP32 mix)
- Outputs a customized TensorRT engine with improved latency + accuracy

---

## 📦 Project Modules

```
trt-llm-surgery/
├── profiler/
│   ├── extract_layer_timings.py        # Parse TensorRT logs or use NVTX to get layer time
│   ├── visualize_hot_layers.ipynb      # Visual heatmap of slowest layers per sequence length
│
├── optimizer/
│   └── precision_optimizer.py          # Algorithm to select best precision per layer
│
├── engine_builder/
│   └── build_trt_engine_custom_precision.py
│
├── runtime/
│   ├── test_inference_latency.py       # Compare vanilla vs. optimized engine
│   └── memory_plot_generator.py
│
├── model/
│   └── mistral7b_onnx/ → (or llama3)
│
├── docs/
│   ├── architecture_diagram.png
│   └── before_after_latency_chart.png
│
└── README.md
```

---

## 💥 Key Technical Highlights

| Capability                   | What It Demonstrates                            |
|------------------------------|-------------------------------------------------|
| Layer-level NVTX + profiler  | Identifies and debugs CUDA kernel bottlenecks   |
| Dynamic shape / batch        | Supports efficient inference under real inputs  |
| Precision fallback           | Maintains accuracy with quantized execution     |
| Engine customization         | Adapts engine behavior to deployment needs      |
| Memory profiling + charts    | Visualizes runtime bottlenecks and improvements |
>>>>>>> b2cfb7c (Initial commit with README)
