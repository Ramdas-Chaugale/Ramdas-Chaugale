# Ramdas Chaugale

MSc Artificial Intelligence, Queen's University Belfast. Based in Belfast, looking for a
first role in machine learning or data. Right to work in the UK, no sponsorship needed.

Most of my work is medical imaging and full-stack AI. I like problems where someone
actually uses the thing at the end.

---

### Retinal lesion segmentation
[retinal-lesion-segmentation](https://github.com/Ramdas-Chaugale/retinal-lesion-segmentation)
· Python, PyTorch, OpenCV

My MSc dissertation, commissioned by a preclinical research company. They were measuring
laser lesions in eye scans by hand, which is slow and two people never draw the same
outline. I built a pipeline that does it automatically and handed them a tool they run
themselves.

0.850 Dice against expert annotation, from 74 labelled images.

The part I would point at is section 5. I compared five models over ten runs, and with
fifteen validation scans the gaps between the leading ones sat inside the run to run
noise. So I reported them as indistinguishable rather than picking the best number, and
told the client that more annotation would help them more than a different network. Every
figure in the repository can be recomputed from the stored measurements.

No scans or weights are published. The imaging data belongs to the partner.

### EduTech AI
[edutech-ai](https://github.com/Ramdas-Chaugale/edutech-ai) ·
[live](https://edutech-ai-dusky.vercel.app/) · Next.js, TypeScript, LangGraph, Prisma,
PostgreSQL

A learning platform running live on Vercel. Four stage agent pipeline behind a Next.js
app. The bit I am happiest with is the service layer over two LLM providers: retry,
exponential backoff and a fallback path, so it keeps working when one of them rate limits
me.

### The Cut Point
[the-cut-point](https://github.com/Ramdas-Chaugale/the-cut-point) · FastAPI, Next.js,
MediaPipe, Docker

Face shape analysis and hairstyle try on. Face geometry is computed in the browser from
468 landmarks, so no photograph leaves the device. Natural language search over the
catalogue, a stylist assistant that cites its sources, and booking. 133 backend tests
under CI.

---

### Tools

Python, PyTorch, OpenCV, NumPy, SciPy, scikit-learn, Pandas
TypeScript, React, Next.js, Node.js, FastAPI, Flask
PostgreSQL, Prisma, Docker, Git, Linux, HPC and Slurm, AWS, GCP

### Elsewhere

[LinkedIn](https://www.linkedin.com/in/ramdas-chaugale-608b3b2a4/) ·
ramdaschaugale33@gmail.com

Some repositories here are forks I kept while learning. The three above are my own work.
