<p align="center" width="100%">
<img src="assets/logo.png" alt="Owl" style="width: 28%; min-width: 150px; display: block; margin: auto;">
</p>

[![Data License](https://img.shields.io/badge/Data%20License-Apache_2.0-green.svg)](https://github.com/aidarmyrzakhan/Atlas-A-LLM-Inquiry-Principle-Benchmark/blob/main/LICENSE.md)
[![Python 3.10+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

# ATLAS: An LLM Inquiry Principle Benchmark

This repository contains resources and research on formulating effective queries and prompts for large language models (LLMs). The primary contribution is the introduction of 26 guiding principles aimed at optimizing interactions with LLMs of various scales, such as LLaMA-1/2, GPT-3.5, and GPT-4.

[//]: # (![demo]&#40;assest/demo.png | width=100&#41;)
[<img src="assets/demo.png" width="750" />](./assets/demo.png)

## Overview

Our work aims to simplify the underlying concepts of formulating questions for different scales of large language models. By examining their abilities and enhancing user comprehension, we focus on optimizing the design of instructions and prompts. Extensive experiments conducted on models like LLaMA-1/2 and GPT-3.5/4 have verified the effectiveness of the proposed principles. 

[//]: # (![distribution]&#40;assets/distribution.png | width=100&#41;)
[<img src="assets/distribution.png" width="750" />](./assets/distribution.png)

## Data Release

Our dataset, comprising 12.5k data points, supports the study of LLM prompting principles. The data is curated to facilitate understanding and application of the [`26 principles`](./data/README.md). 
Our project includes two types of datasets, catering to different needs and research focuses:

   1. **General Dataset (`general_dataset.json`)**: This comprehensive dataset combines all the examples from each of the 26 principles into a single file, offering a holistic view of our research and its diverse applications.
   
      - File: [`general_dataset.json`](./data/general_dataset.json)
      - Structure:
        - Each entry contains an `instruction` field describing the task.
        - The `output` field provides the model-generated response to the instruction.
   
      Example:
      ```json
      {
       "instruction": "If you were an expert economist, how would you answer: What are the key differences between a capitalist and a socialist economic system?",
       "output": "As an expert economist, I would describe the key differences between capitalist and socialist economic systems along several dimensions:..."
      }
   
   2. **Individual Principle Datasets (`principle_{i}.json`)**: We offer separate datasets for each of the 26 principles for a more focused study. These files allow researchers to explore and analyze data of specific principles in isolation.
   
      - Files: `principle_1.json`, `Principle_2.json`, ..., `Principle_26.json`
      Each file follows the same structure as the general dataset but contains examples only related to the respective principle.


## Data Generation
For our project, we initially crafted a set of principled, foundational questions manually to establish a robust baseline. These questions were carefully crafted to cover a wide range of topics and complexities, ensuring a comprehensive starting point for our instruction generation process. Following this, we used the GPT-4 API to expand our question repository. It was tasked with generating new questions that were semantically and thematically related to our manually created ones.

To generate instructions based on the principles:
   ```
   python generate.py
   ```


## Principled Instruction Finetuning

Our benchmark is compatible with [Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca) or [FastChat](https://github.com/lm-sys/FastChat). We will further provide the finetuned models.

## Citation

```
@article{bsharat2023principled,
  title={Principled Instructions Are All You Need for Questioning LLaMA-1/2, GPT-3.5/4},
  author={Sondos Mahmoud Bsharat, Aidar Myrzakhan, Zhiqiang Shen},
  journal={arXiv preprint arXiv:2312.16171},
  year={2023},
}
```


## Contributing
We welcome contributions and suggestions to improve our principles and expand the dataset.

## Acknowledgements

[Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca)
