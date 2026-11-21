<picture>
  <source media="(max-width: 600px)" srcset="./assets/hero-compact.svg">
  <img src="./assets/hero.svg" width="100%" alt="Harshit Singh · Software engineer · Backend systems, AI and automation">
</picture>

# I follow the request all the way through.

I’m Harshit, a software engineer in Pune. I build the parts of a system you notice when something goes wrong. In my [HTTP load balancer](https://github.com/ashoka0402/Adaptive-L7-Load-Balancer), that means routing around a backend that still answers health checks but has started to slow down. In [Relay](https://github.com/ashoka0402/browser-automation), it means being able to open a failed browser step and see exactly what it did.

Previously **AI Backend Engineering Intern at Ethara AI**. Finishing my **B.Tech in Computer Science at Bharati Vidyapeeth, Pune, in 2027**. Open to backend, AI systems and full-stack engineering roles.

[LinkedIn](https://www.linkedin.com/in/harshit-singh-a830b3285/) · [Email me](mailto:ashoka0402har@gmail.com) · [Engineering projects](#selected-engineering-work) · [What I’m building now](#on-my-workbench)

<img src="./assets/divider.svg" width="100%" alt="">

## Selected engineering work

### <img src="./assets/icons/route.svg" width="25" alt=""> Adaptive L7 Load Balancer

**Implemented and benchmarked** · Python, asyncio, aiohttp, Prometheus, Grafana

A healthy server can still be the wrong place to send the next request. I built four routing policies into an asynchronous HTTP proxy. The adaptive policy weighs smoothed response time against active connections, so a fast backend becomes less attractive as it fills up. Connection pooling, backpressure and circuit breakers handle different ways the upstream pool can run out of capacity.

<img src="./assets/routing-example.svg" width="630" alt="Illustrative routing decision. Backend B wins despite its slower 15 ms latency because it has 5 active connections to A’s 50.">

**4,970.93 requests/s · 8.25 ms median latency.** The repo documents this example against a local endpoint with 100 concurrent workers over 15 seconds.

[Repository](https://github.com/ashoka0402/Adaptive-L7-Load-Balancer) · [Routing policy](https://github.com/ashoka0402/Adaptive-L7-Load-Balancer/blob/main/app/routing/latency_aware.py) · [Benchmark runner](https://github.com/ashoka0402/Adaptive-L7-Load-Balancer/blob/main/benchmarks/run_benchmarks.py)

### <img src="./assets/icons/workflow.svg" width="25" alt=""> Relay

**Working browser automation platform** · Next.js, React Flow, Liveblocks, Trigger.dev, Stagehand, Steel

Two people can edit the same workflow, then watch it drive a browser. I separated the collaborative canvas from the background runner. The runner orders nodes by dependency, passes structured output from one step to the next and records each step’s duration, result or error. That gives “the agent got stuck” a specific place to start debugging.

[Repository](https://github.com/ashoka0402/browser-automation) · [Workflow executor](https://github.com/ashoka0402/browser-automation/blob/main/features/workflows/tasks/run-workflow.ts)

### <img src="./assets/icons/forecast.svg" width="25" alt=""> Aeris

**Final-year project in development** · LightGBM, DuckDB, FastAPI, Next.js, MapLibre

A ward map can make an uncertain forecast look precise. I’m building a Pune and Delhi air-quality platform that combines station readings, weather and fire data, and shows a range for PM2.5 at **24, 48 and 72 hours**. After a model struggled with a seasonal shift, the project switched to predicting the change from a recent observation. A 30-day rolling-origin backtest compares forecasts with persistence and climatology. Evaluation to date covers **Delhi**. Pune validation is still open.

[Repository](https://github.com/ashoka0402/final_year_project) · [Forecast model](https://github.com/ashoka0402/final_year_project/blob/main/vayu_core/forecast/model.py) · [Evaluation protocol](https://github.com/ashoka0402/final_year_project/blob/main/vayu_core/forecast/backtest.py)

### <img src="./assets/icons/review.svg" width="25" alt=""> PR Review Agent

**Implemented GitHub App** · Python, FastAPI, GitHub webhooks, Bandit, Radon

I wanted an automated reviewer whose comments a developer could check against the diff. The app combines static checks with a model review, scores risk from the findings and posts feedback on the pull request. A security finding, a complex change and a large diff each contribute separately to that score.

[Repository](https://github.com/ashoka0402/pr-review-agent) · [Risk scoring](https://github.com/ashoka0402/pr-review-agent/blob/main/app/review/scorer.py) · [Example review](https://github.com/ashoka0402/pr-review-agent/blob/main/docs/images/pr-review.png)

### <img src="./assets/icons/shared.svg" width="25" alt=""> ONE / MANY

**Hackathon prototype** · Next.js, FastAPI, PostgreSQL, Gemini, PayPal Sandbox

Two people need a drill on different weekends. ONE / MANY matches their requests, splits a quote in exact cents and lets each person authorize a Sandbox contribution. Gemini extracts what each person needs. The server verifies payment captures for the contribution ledger, and a PostgreSQL exclusion constraint prevents overlapping bookings even if two members reserve at once.

[Repository](https://github.com/ashoka0402/ONE-MANY) · [Booking constraint](https://github.com/ashoka0402/ONE-MANY/blob/main/apps/api/alembic/versions/20261112_05_asset_reservations.py) · [Passing CI run](https://github.com/ashoka0402/ONE-MANY/actions/runs/43170611672)

<img src="./assets/divider.svg" width="100%" alt="">

## Experience and open source

- **Ethara AI · AI Backend Engineering Intern.** I built FastAPI services for annotation workflows, used YOLO to suggest labels, and moved annotation records from JSON into PostgreSQL so reviewed data could be exported for RLHF training.
- **Lecture search · [YouTube Lecture RAG](https://github.com/ashoka0402/Youtube_Transcription_RAG).** I indexed **126 lecture transcripts** with faster-whisper, SentenceTransformers and Qdrant. Search results take a student to the second a concept was taught. Stable chunk IDs let me rerun ingestion without duplicating the index.
- **Developer tools · [venvkill on PyPI](https://pypi.org/project/venvkill/).** I published a Python CLI that finds forgotten virtual environments and ranks them by size, age and condition. A dry run lets the developer inspect what would be removed.
- **Scientific software · [A2rchi / archi fork](https://github.com/ashoka0402/archi).** I explored this research assistant through the HEP Software Foundation. My work focused on Chroma collection collisions and concurrent writes to JSON files.
- **Hackathons.** I led **i-Vision**, one of five finalist teams for **SIH 2024 problem SIH1715**, and led a **PAN IIT Imagine Top 20** team. At SIH, our model failed shortly before judging. We split three alternatives across the team, tested them in parallel and had a working model to show. [Team announcement](https://www.linkedin.com/posts/harshit-singh-a830b3285_sih2024-smartindiahackathon-sihgrandfinale-activity-7263245291967946752-abu5)

## Tools I reach for

| Domain | Tools I’ve used in these systems |
| --- | --- |
| <img src="./assets/icons/code.svg" width="16" alt=""> Languages and APIs | Python, TypeScript, SQL, C++, FastAPI, asyncio |
| <img src="./assets/icons/data.svg" width="16" alt=""> Models and data | LightGBM, YOLO, faster-whisper, SentenceTransformers, PostgreSQL, DuckDB, Qdrant |
| <img src="./assets/icons/workflow.svg" width="16" alt=""> Interfaces and automation | Next.js, React Flow, MapLibre, Liveblocks, Trigger.dev, Stagehand |
| <img src="./assets/icons/ops.svg" width="16" alt=""> Infrastructure and observability | Docker, AWS S3 and EC2, GitHub Actions, Prometheus, Grafana |

I also solve contest problems on [LeetCode](https://leetcode.com/u/harshitsingh04/) and [Codeforces](https://codeforces.com/profile/Harshitsingh04).

## On my workbench

**AI Group Friends** is a voice room for one person and four AI friends. I want to be able to interrupt one friend halfway through a sentence, address another by name and hear the right one pick up the thread. I’m prototyping turn-taking, cancellation of queued audio and the delay until the next voice starts.

**How I work.** I like to write down what a user should observe when the system fails. For a shared booking, I can send two overlapping reservations at once and check whether both get through. For voice, the equivalent test is whether an interrupted speaker’s last few words still play. Those small tests tell me where the architecture needs work.

<details>
<summary><strong>Public pull-request activity</strong></summary>

[![Monthly counts of public pull requests opened by ashoka0402 over the six months shown](./assets/activity.svg)](https://github.com/search?q=is%3Apr+is%3Apublic+author%3Aashoka0402&type=pullrequests)

</details>

<img src="./assets/divider.svg" width="100%" alt="">

If your team builds backend infrastructure, AI tools or automation that people depend on, I’d be glad to walk through a design decision, a benchmark or a pull request together. [Get in touch](mailto:ashoka0402har@gmail.com) · [Connect on LinkedIn](https://www.linkedin.com/in/harshit-singh-a830b3285/)
