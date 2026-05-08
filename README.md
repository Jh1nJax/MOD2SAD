# MOD²SAD: Enhancing Malicious Office Document Detection through Semantic Aware Deobfuscation

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Paper](https://img.shields.io/badge/Paper-Coming%20Soon-brightgreen)](#citation)

This repository contains the official implementation, dataset hashes, and evaluation code for the paper: **"MOD²SAD: Enhancing Malicious Office Document Detection through Semantic Aware Deobfuscation"**.

## 📖 Introduction

Advanced Persistent Threat (APT) campaigns heavily rely on malicious Office documents as initial infection vectors. Modern adversaries employ sophisticated semantic obfuscation techniques (e.g., logic fragmentation, control flow flattening, and multi-layered encoding) to bypass traditional static analysis and evade dynamic sandboxing. 

**MOD²SAD** is a novel static analysis framework centered on semantic-aware code reconstruction. By leveraging the deep semantic comprehension of Large Language Models (LLMs), our framework acts as a "semantic aligner" to actively recover the underlying execution logic of heavily obfuscated macros (VBA/XLM) without the need for risky dynamic execution. It significantly outperforms conventional static tools in extracting hidden Indicators of Compromise (IoCs) and achieves a peak detection accuracy of 98.89% when integrated with Machine Learning classifiers.

## 🏗️ Framework Architecture

The MOD²SAD framework consists of four primary modules:

1. **Preliminary:** Securely extracts raw macro segments (VBA and XLM) from various document structures (OLE and OOXML) and decrypts default-password-protected files automatically.
2. **OASA (Obfuscation Awareness and Splitting Approach):** Quantifies the obfuscation level of each macro segment. To prevent LLM cognitive overload and hallucination (the "Repeat Trap"), it optimally partitions long, complex scripts into structured chunks using an adaptive sliding window.
3. **Deobfuscation (Semantic Reconstruction):** Employs generative LLMs guided by Semantic Reconstruction Constraints (SRC) to resolve string concatenations, evaluate encoded expressions, and expose hidden IoCs while preserving the original malicious intent.
4. **Detection:** Extracts a 53-dimensional static feature vector using a frequency-based Count strategy and employs robust Machine Learning classifiers (e.g., Random Forest, XGBoost) for highly accurate malicious document identification.


## ⚙️ Installation

[Please detail the required environment, e.g., `pip install -r requirements.txt`, required Python version, and any specific setup instructions for PyCaret, OleVBA, or LLM SDKs like Ollama/OpenAI API here.]

## 🚀 Usage

[Please describe how to run your code here. For example:
- How to configure the LLM API keys.
- How to run the OASA module.
- How to execute the full pipeline on a sample document.
- Example command-line usage: `python main.py --file sample.doc --model qwen3-coder`]

## 📜 Citation

If you find this code, dataset, or framework useful for your research, please cite our paper:

```bibtex
@article{mod2sad2026,
  title={MOD SAD: Enhancing Malicious Office Document Detection through Semantic Aware Deobfuscation},
  author={},
  journal={[Scientific Reports]},
  year={[2026]},
  publisher={[Springer]}
}
