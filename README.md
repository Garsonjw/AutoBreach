# AutoBreach: Universal and Adaptive Jailbreaking with Efficient Wordplay-Guided Optimization

## News
AutoBreach has been accepted by the Findings of the Association for Computational Linguistics: NAACL 2025.
## Overview
<img src="./img/overview.jpg" alt="Overview" width="1000" height="300">
Despite the widespread application of large language models (LLMs) across various
tasks, recent studies indicate that they are susceptible to jailbreak attacks, which can
render their defense mechanisms ineffective. However, previous jailbreak research
has frequently been constrained by limited universality, suboptimal efficiency, and
a reliance on manual crafting. In response, we rethink the approach to jailbreaking
LLMs and formally define three essential properties from the attacker’s perspective,
which contributes to guiding the design of jailbreak methods. We further introduce
AutoBreach, a novel method for jailbreaking LLMs that requires only black-box
access. Inspired by the versatility of wordplay, AutoBreach employs a wordplayguided mapping rule sampling strategy to generate a variety of universal mapping
rules for creating adversarial prompts. This generation process leverages LLMs’
automatic summarization and reasoning capabilities, thus alleviating the manual
burden. To boost jailbreak success rates, we further suggest sentence compression
and chain-of-thought-based mapping rules to correct errors and wordplay misinterpretations in target LLMs. Additionally, we propose a two-stage mapping rule
optimization strategy that initially optimizes mapping rules before querying target
LLMs to enhance the efficiency of AutoBreach. AutoBreach can efficiently identify
security vulnerabilities across various LLMs, including three proprietary models:
Claude-3, GPT-3.5, GPT-4 Turbo, and two LLMs’ web platforms: Bingchat, GPT-4
Web, achieving an average success rate of over 80% with fewer than 10 queries.


## Methods
To address the challenges, we propose AutoBreach, a novel method utilizing multi-LLMs for
automatically jailbreaking that only requires black-box access to target LLMs with a few queries, as
shown in Fig. 1. To enhance universality and adaptability, we introduce wordplay-guided mapping
rule sampling that generates innovative and diverse wordplay mapping rules. Specifically, inspired by
the universality of wordplay strategies [2, 21, 23, 25], AutoBreach leverages the inductive reasoning
of an LLM (Attacker) about wordplay to generate a variety of universal mapping rules, requiring
no human intervention. Furthermore, due to errors from long sentences and misinterpretations of
wordplay by target LLMs, we propose sentence compression and chain-of-thought-based (CoTbased) mapping rules which refine jailbreak goals and enhance the comprehension of target LLMs
to enhance jailbreak success rates (JSR). To ensure efficiency, we propose a two-stage mapping
rule optimization. The core idea is the interaction between the roles of Attacker and Supervisor
to execute an initial optimization stage. By this stage before iteratively refining the mapping rule
through querying target LLMs, which efficiently enhances performance and reduces queries.


## Performance
<img src=".\img\tab1.png">
Tab. 1: A comparison of jailbreaking methods evaluates universality, adaptability, and efficiency. L: Low, exceeding 50 queries; M: Mid, exceeding 20 queries; H: High, within 10 queries.

<img src=".\img\tab2.jpg" alt="tab2" width="1000" height="350">
Tab. 2: Jailbreak attacks on the AdvBench subset. JSR and Queries represent the jailbreak success
rate (JSR) and average number of queries, respectively. Since GCG requires white-box access, we
can only report its results on open-sourced models. * denotes results derived from the original source. †[3, 11, 13] is in the same way. In each column, the best results are bolded.

## Example
<img src=".\img\demo.jpg">
Run the `./llm_main.py` script to test the performance of AutoBreach.

First, you need to add your OpenAI API key to system environment variables. The method to do this depends on your operating system and the shell you're using.

**For Bash shell (Linux, macOS, Git Bash on Windows):**

```bash
# Export your OpenAI API key
export OPENAI_API_KEY=<insert your OpenAI API key>
OPENAI_API_BASE_URL=<inert your OpenAI API BASE URL>  #(Should you utilize an OpenAI proxy service, kindly specify this)
```

**For Windows Command Prompt:**

```cmd
REM export your OpenAI API key
set OPENAI_API_KEY=<insert your OpenAI API key>
set OPENAI_API_BASE_URL=<inert your OpenAI API BASE URL>  #(Should you utilize an OpenAI proxy service, kindly specify this)
```

**For Windows PowerShell:**

```powershell
# Export your OpenAI API key
$env:OPENAI_API_KEY="<insert your OpenAI API key>"
$env:OPENAI_API_BASE_URL="<inert your OpenAI API BASE URL>"  #(Should you utilize an OpenAI proxy service, kindly specify this)

```

Replace `<insert your OpenAI API key>` with your actual OpenAI API key in each case. Make sure there are no spaces around the `=` sign.

After setting the OpenAI API key, you can run the script:

```bash
python llm_main.py
```



## Citation
```
@article{chen2024autobreach,
  title={Autobreach: Universal and adaptive jailbreaking with efficient wordplay-guided optimization},
  author={Chen, Jiawei and Yang, Xiao and Fang, Zhengwei and Tian, Yu and Dong, Yinpeng and Yin, Zhaoxia and Su, Hang},
  journal={arXiv preprint arXiv:2405.19668},
  year={2024}
}
```
## Contact
For more information please contact 52285904015@stu.ecnu.edu.cn.
