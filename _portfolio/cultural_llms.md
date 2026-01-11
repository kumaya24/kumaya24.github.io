---
title: "Cross-Cultural Evaluation of LLMs"
excerpt: "A case study on Chinese-to-English movie title translation, analyzing how models like GPT-4 handle cultural nuances versus literal accuracy."
collection: portfolio
---

**Role:** Lead author (in collaboration with [Jialing Wu](https://eed.osu.edu/people/wu.6489) and [Yingyu Cheng](https://stat.osu.edu/people/cheng.1753))

**Advisor:** [Prof. Sachin Kumar](https://shocheen.github.io/)

**Code:** [View on GitHub](https://github.com/kumaya24/cse5525-llm-cross-cultural-eval)

**Status:** In Preparation (Targeting Feb 2026 Submission)

### Project Overview
LLMs excel at literal translation, but do they understand cultural context? In this project, we evaluated the performance of selected models on translating Chinese movie titles, which are dense with cultural idioms. We tested 3 prompting strategies: **Title-only**, **Title + Synopsis**, and **Culture-aware**.

### 1. Quantitative Analysis
We measured performance using 4 metrics (Cosine Similarity, BERTScore, BLEURT, and our custom CSI-Match) as shown below.

<div style="display: flex; justify-content: space-between; flex-wrap: wrap; gap: 10px; margin-bottom: 20px;">
  <div style="flex: 1; min-width: 300px;">
    <img src="/images/csi_match.png" alt="CSI Match Chart" style="width: 100%; border-radius: 5px;">
    <p style="text-align: center; font-size: 0.8em; color: gray;">Fig 1: CSI-Match Performance (Cultural Accuracy)</p>
  </div>
  <div style="flex: 1; min-width: 300px;">
    <img src="/images/bertscore.png" alt="BERTScore Chart" style="width: 100%; border-radius: 5px;">
    <p style="text-align: center; font-size: 0.8em; color: gray;">Fig 2: BERTScore Performance (General Semantics)</p>
  </div>
</div>

### 2. Qualitative Analysis: Adaptation Strategies
We categorized every translation output into 4 strategies. The distribution below shows a heavy bias toward literal translation.

<img src="/images/qualitative.png" alt="Strategy Distribution" style="display: block; margin: 0 auto 20px auto; width: 80%; border-radius: 5px;">
<p style="text-align: center; font-size: 0.8em; color: gray; margin-top: -15px;">Fig 3: Distribution of adaptation strategies (GPT-4 with Synopsis)</p>

### Key Findings

* **Context Unlocks Cultural Reasoning:**
    Quantitative analysis revealed a massive performance gap between prompt types. Providing a **synopsis** alongside the title significantly increased the model's ability to handle cultural items (CSI-Match rose from 0.64 to 0.80). Without context, models often hallucinated culturally plausible but incorrect meanings.

* **The "Safe" Literalism Bias:**
    As shown in **Fig 3**, models overwhelmingly favor **Preservation** (56.8% of cases), defaulting to literal translations. While effective for simple titles, this strategy fails for idioms.
    * *Example:* GPT translated 《卧虎藏龙》as *Crouching Tiger, Hidden Dragon* literally, missing the underlying idiom about "undiscovered talent".
    * *Success:* However, when prompted with context, GPT successfully transformed 《天涯明月刀》（literal "Heaven's Edge, Bright Moon, Blade") into *The Magic Blade* to match "Wuxia theme" as the "heroic" genre tropes rather than using a stiff literal translation.

### Technical Stack
* **Models:** GPT-4, Llama 2, Gemini-2.5