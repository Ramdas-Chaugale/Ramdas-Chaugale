<div align="center">

# Ramdas Chaugale

**MSc Artificial Intelligence, Queen's University Belfast**

Medical imaging and full-stack AI. I like problems where someone actually uses the thing at the end.

<img src="https://img.shields.io/badge/Belfast,_UK-0A66C2?style=flat-square&logo=googlemaps&logoColor=white" alt="Belfast" />
<img src="https://img.shields.io/badge/Medical_imaging-5C3EE8?style=flat-square" alt="Medical imaging" />
<img src="https://img.shields.io/badge/Full--stack_AI-2F9E44?style=flat-square" alt="Full stack AI" />

<a href="https://www.linkedin.com/in/ramdas-chaugale-608b3b2a4/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="mailto:ramdaschaugale33@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>

</div>

---

## What I build

<details open>
<summary><b>Retinal lesion segmentation</b> &nbsp;·&nbsp; a tool a research company runs on their own scans</summary>

<br>

[**retinal-lesion-segmentation**](https://github.com/Ramdas-Chaugale/retinal-lesion-segmentation)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![Linux](https://img.shields.io/badge/HPC_and_Slurm-FCC624?style=flat-square&logo=linux&logoColor=black)

My MSc dissertation, commissioned by a preclinical research company. They were measuring
laser lesions in eye scans by hand, which is slow and two people never draw the same
outline. I built a pipeline that does it automatically and handed them a tool they run
themselves.

**0.850 Dice** against expert annotation, from **74 labelled images**.

The part I would point at is the comparison. I trained five models over ten runs, and with
fifteen validation scans the gaps between the leading ones sat inside the run to run noise.
So I reported them as indistinguishable rather than picking the best number, and told the
client that more annotation would help them more than a different network. Every figure in
the repository can be recomputed from the stored measurements.

No scans or weights are published. The imaging data belongs to the partner.

</details>

<details>
<summary><b>backstop</b> &nbsp;·&nbsp; guardrails and an evaluation harness for a tool calling agent</summary>

<br>

[**backstop**](https://github.com/Ramdas-Chaugale/backstop)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Pytest](https://img.shields.io/badge/evals-20_passing-1b6b4a?style=flat-square)

A customer support agent with three tools, and the three things around it that actually
matter: guardrails that run **before** a tool executes, twenty adversarial test
conversations, and a baseline gate that fails the build when behaviour drifts.

An agent evaluation suite that calls a live model cannot run in CI. It costs money on every
push and gives a different answer each time. So the model layer records each call once,
keyed by a hash of the conversation, and replays from disk. CI runs free, offline and
deterministic.

The suite found two faults in my own guardrails on its first full run. One rule checked a
confirmation field that nothing in the system ever wrote to. Another was registered against
tools, so it could never fire on a turn that called no tool. Both are written up in the
README, because a rule that cannot fire still reads like protection in a code review.

</details>

<details>
<summary><b>jobfit</b> &nbsp;·&nbsp; retrieval over real job ads, built to be measured</summary>

<br>

[**jobfit**](https://github.com/Ramdas-Chaugale/jobfit)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX_Runtime-005CED?style=flat-square&logo=onnx&logoColor=white)
![Tests](https://img.shields.io/badge/tests-66_passing-1b6b4a?style=flat-square)

Ask in plain English, get the roles that match, each with the sentence from the ad that
justifies it. 135 ads I labelled by hand, 61 queries I wrote, three query families kept
apart so an easy one cannot hide a failure in a hard one.

Measuring it properly found two bugs in my own code before it said anything about the
model. A corpus filter running at 21% precision, because `llm` matched inside
*fulfillment* and 121 of 135 ads mention AI. And a third of all chunks carrying no
requirement signal at all.

It also found that a plain keyword baseline beat my embedding model on two of three query
families. That is in the README, because a finding I did not want is still a finding.

The web interface puts all six retrievers side by side on the same query, so the thing the
numbers claim is something you can watch happen.

</details>

<details>
<summary><b>EduTech AI</b> &nbsp;·&nbsp; a learning platform running live on Vercel</summary>

<br>

[**edutech-ai**](https://github.com/Ramdas-Chaugale/edutech-ai) &nbsp;·&nbsp; [**live demo**](https://edutech-ai-dusky.vercel.app/)

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

A four stage agent pipeline behind a Next.js app, deployed and running.

The bit I am happiest with is the service layer over two LLM providers: retry, exponential
backoff and a fallback path, so it keeps working when one of them rate limits me.

</details>

<details>
<summary><b>The Cut Point</b> &nbsp;·&nbsp; face shape analysis where no photo leaves your device</summary>

<br>

[**the-cut-point**](https://github.com/Ramdas-Chaugale/the-cut-point)

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

Face shape analysis and hairstyle try on. The face geometry is computed in the browser from
468 landmarks, so no photograph leaves the device.

Natural language search over the catalogue, a stylist assistant that cites its sources, and
salon booking. 139 backend tests under CI.

</details>

---

## Tools I reach for

<details open>
<summary>Click to fold away</summary>

<br>

| | |
|---|---|
| **Machine learning** | ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white) |
| **Data** | ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) |
| **Web** | ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) |
| **Everything else** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) |

</details>

---

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=Ramdas-Chaugale&show_icons=true&hide_border=true&hide=issues&theme=github_dark&hide_title=true" />
  <img src="https://github-readme-stats.vercel.app/api?username=Ramdas-Chaugale&show_icons=true&hide_border=true&hide=issues&hide_title=true" alt="GitHub stats" height="150" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=Ramdas-Chaugale&layout=compact&hide_border=true&theme=github_dark&exclude_repo=suzieq,attack-navigator,Student-Progress-Analyzer,Water-consumption-forecast&hide_title=true" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ramdas-Chaugale&layout=compact&hide_border=true&exclude_repo=suzieq,attack-navigator,Student-Progress-Analyzer,Water-consumption-forecast&hide_title=true" alt="Top languages" height="150" />
</picture>

</div>

---

<sub>Some repositories here are forks I kept while learning. The five above are my own work.</sub>
