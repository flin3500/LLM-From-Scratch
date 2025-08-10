# LLM-From-Scratch
This repository contains concepts and optimization techniques related to LLMs, covering both training and inference.

### Training and Inference

- Training
- Inference
    - Optimisation Technology
        - Memory Level
            - KV Cache
        - Kernel Level
    - Framework: vLLM, SGlang, TensorRT LLM
    - Important Configs Metrics and formula
        - Configs
            - Concurrency
            - Max Batch Size
            - Max Num Tokens
        - Metrics
            - Throughput (Output Tokens per second)
            - Time to First Token Latency (TTFT)
                - Affects: input sequence length
            - Time per Output Token Latency (TPOT)
                - Affects: input sequence length, output sequence length
        - Formula
            - E2E Latency:
                - Small concurrency: (TTFT + TPOT * (Output sequence length -1)) * (num of requests / concurrency) = E2E Latency
                - Large concurrency: (TTFT + TPOT * (Output sequence length -1)) * (num of requests / concurrency) + Scheduler overhead = E2E Latency
            - Output Tokens per second
                - (Output sequence length * num of requests) / E2E latency(s)  = Output Tokens per second

Examples

- DeepSeek
- Llama
