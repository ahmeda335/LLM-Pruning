# 🧬 Pruning Large Language Models with Genetic Algorithms

This repository contains the source code and experimental setup for our research paper:

**"Launching the Power of Genetic Algorithms in Pruning Large Language Models"**  
_Ahmed Adel Mohamed, Ahmed Amr El Hefnawy, Mohamed Aita_  
Faculty of Engineering, Tanta University, Egypt.

---

## 📝 Abstract

Large Language Models (LLMs) have achieved remarkable results in NLP tasks but come with immense computational and energy demands. This work proposes a novel layer-level **structured pruning** approach using **Genetic Algorithms (GAs)** to automatically search for optimal sets of redundant or underutilized layers to prune. Our method strikes a balance between computational efficiency and task performance without requiring retraining.

---

## 🧠 Methodology

- **Structured Pruning**: Removes whole layers while preserving model shape.
- **Genetic Algorithm Components**:
  - **Initialization**: Randomly generate a population of pruned models.
  - **Selection**: Choose high-performing candidates.
  - **Crossover**: Mix layer configurations between models.
  - **Mutation**: Introduce random changes for exploration.
- **Evaluation**: Custom metric (average of squared task scores) to emphasize performance differences.

---

## 🧪 Experiments

- **Base Models**:
  - LLaMA 3.1 8B
  - InternLM 2.5 7B
- **Benchmarks**: Zero-shot and Few-shot evaluation on:
  - HellaSwag
  - Mutual
  - OpenBookQA
  - TruthfulQA-MC2
- **Tools & Libraries**:
  - [Huggingface Transformers](https://github.com/huggingface/transformers)
  - [DEAP](https://github.com/DEAP/deap) (Genetic Algorithm)
  - [MergeKit](https://github.com/arcee-ai/mergekit) (Model merging after pruning)

---

## 📈 Results Summary

- Pruning up to 16 layers reduced model size significantly.
- Some tasks showed improved performance after pruning.
- Early layers (e.g., 0–2) are critical for model performance.
- Deep layers can often be pruned with minimal accuracy loss.

---

## ⚙️ GA Parameters

| Parameter        | Value        |
|------------------|--------------|
| Crossover Method | `cxOnePoint` |
| Mutation Method  | `mutUniformInt` |
| Selection        | `selTournament` |
| Probabilities    | Crossover: 0.5, Mutation: 0.5 |

---

## 📌 Key Observations

- Not all layers contribute equally—some can be pruned to improve performance.
- Pruning reduces hallucinations and overfitting in specific tasks.
- The approach is extensible to finer-grained or partial-layer pruning.

---

## 📚 Citation

If you use this codebase or findings, please cite our work:

```bibtex
@misc{adel2025geneticpruning,
  title={Launching the Power of Genetic Algorithms in Pruning Large Language Models},
  author={Ahmed Adel Mohamed and Ahmed Amr El Hefnawy and Mohamed Aita},
  year={2025},
  institution={Faculty of Engineering, Tanta University},
}
```

---

## 📬 Contact

For feedback, suggestions, or collaboration:

- 📧 **Dr. Mohamed Aita** – Mohammad.eita@f-eng.tanta.edu.eg
- 📧 **Ahmed Adel Mohamed** – UG_31093295@f-eng.tanta.edu.eg 
- 📧 **Ahmed Amr El Hefnawy** – UG_31093612@f-eng.tanta.edu.eg

---

🧠 *Optimizing LLMs for a smarter and more sustainable future.*
