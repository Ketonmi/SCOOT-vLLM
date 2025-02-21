### SCOOT: SLO-Oriented Performance Tuning for LLM Inference Engines

This is the implementations of the WWW2025 oral paper [SCOOT: SLO-Oriented Performance Tuning for LLM Inference Engines](https://arxiv.org/abs/2408.04323) 

![](SCOOT.jpg)

### Overview

SCOOT is an automatic performance tuning system to optimize SLOs for each LLM inference service by tuning the parameters of the inference engine. It jointly exploits single-objective and multiple-objective Bayesian optimization techniques to handle various optimization objectives via exploration and exploitation. Moreover, SCOOT prunes the searchb space with known constraints and adopts a random forest to learn hidden constraints during the tuning process to mitigate invalid exploration. It can improve the performance of the LLM inference engine efficiently.

### Quick Start
`bo_scoot.py` is the script invovling the whole pipeline.

The shell script `tune_entry.sh` is used to reproduce the main results in the paper.

The python scripts in the directory `clients` are forked form vllm, involving `api_server.py`, `backend_request_func.py` and `benchmark_serving.py`, which are used to initialize server, client and benchmarking requsting, respectively.


Also, we implement hidden and hard constraits in the BO search based on HEBO, which is in `hebo` directory. Specifically, the hidden and hard constraits are incorporated in acquisition functions, i.e., `/hebo/acquisitions/acq.py`.

### Citation
```latex
@article{Cheng2024TowardsSL,
  title={Towards SLO-Optimized LLM Serving via Automatic Inference Engine Tuning},
  author={Ke Cheng and Zhi Wang and Wen Hu and Tiannuo Yang and Jianguo Li and Sheng Zhang},
  journal={ArXiv},
  year={2024},
  volume={abs/2408.04323},
  url={https://api.semanticscholar.org/CorpusID:271768955}
}
```


