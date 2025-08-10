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
              - **Small concurrency**  
  ![Small Concurrency Formula](https://latex.codecogs.com/svg.image?\color{red}\text{E2E%20Latency}=\left(\text{TTFT}+\text{TPOT}\times(\text{Output%20sequence%20length}-1)\right)\times\frac{\text{num%20of%20requests}}{\text{concurrency}})
              - **Large concurrency**  
  ![Large Concurrency Formula](https://latex.codecogs.com/svg.image?\color{red}\text{E2E%20Latency}=\left(\text{TTFT}+\text{TPOT}\times(\text{Output%20sequence%20length}-1)\right)\times\frac{\text{num%20of%20requests}}{\text{concurrency}}+\text{Scheduler%20overhead})
            - Output Tokens per second:   
  ![Output Tokens Formula](https://latex.codecogs.com/svg.image?\color{red}\text{Output%20Tokens/sec}=\frac{\text{Output%20sequence%20length}\times\text{num%20of%20requests}}{\text{E2E%20latency%20(sec)}})

Examples

- DeepSeek
- Llama
