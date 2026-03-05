# ITAI-1378-Midterm_AIVirtualStaging
### RE.AI Solution: AI-Powered Virtual Staging
**Team Member:** Brandon Matias

**Tier:** Tier 2 

**Justification:** This project implements a custom computer vision pipeline using SeeDream 4.5 via API. It features advanced prompt engineering with over 30 style/room combinations and a custom-coded Structural Integrity Rule to prevent architectural hallucinations. It also includes a robust backend with PostgreSQL for job tracking and asynchronous webhook processing.

## Problem Statement
Empty or poorly furnished homes sell slower and for significantly less than staged properties, yet traditional physical staging costs between $2,000–$5,000+. Existing digital tools often "hallucinate" architectural changes, such as moving walls or windows, which can lead to legal and disclosure issues for real estate agents.

## Solution Overview
RE.AI Solution is a web-based platform that instantly transforms empty room photos into realistically furnished, market-ready listings. By utilizing an additive staging pattern, the system ensures 100% architectural integrity—placing furniture and decor strictly on the existing floor plane without altering the home's original structure or lighting.

## Technical Approach
**CV Technique:** Image-to-Image Generation / Inpainting.

**Model:** Primary: SeeDream 4.5 (bytedance/seedream-4.5) Fallback: OpenAI gpt-image-1.

**Framework:** Node.js/Express, Replicate API, and Replit Object Storage.

**Why this approach:** SeeDream 4.5 provides superior structural consistency for architectural photography. The additive prompt engineering ensures that furniture placement is grounded and realistic without the need for manual 3D modeling.

## Dataset
**Source:** Custom-curated prompts based on professional interior design styles (Modern, Contemporary, Rustic, Minimalist, Traditional).

**Size:** 30+ unique room/style prompt combinations.

**Labels:** 6 indoor room types (Living, Bedroom, Kitchen, etc.) and specialized outdoor/garage logic.

## Success Metrics
**Primary Metric:** Structural Accuracy — 0% alteration of walls, windows, and floors (verified via visual audit).

**Secondary Metrics:** Latency — Staged image delivery in under 15 seconds; User Approval Rate via the token system.

## Week-by-Week Plan (Dec 2025 – Jan 2026)

**Dec 3–5:** Foundation: Launched initial showcase, integrated image enhancement, and established pay-per-download security.

**Jan 12:** Accuracy Sprint: Integrated ControlNet for 3D perspective and developed anti-hallucination prompt constraints.

**Jan 19:** Ecosystem: Developed Agent Profile management and public portfolio pages.

**Jan 20:** Optimization: Migrated to SeeDream 4.5, implemented webhook-based pipelines, and finalized specialized garage/outdoor logic.

**Week 15:** Final Presentation.

## Resources Needed
**Compute:** Replicate API for model inference; Replit for web hosting.

**Frameworks:** Hugging Face, Node.js/Express, and Neon/PostgreSQL.

**Cost:** $5–$10 per 100 images (API usage).

## Risks & Mitigation
| Risk | Probability | Mitigation |
| :--- | :--- | :--- |
| **Model Downtime** | Medium | Automated fallback to OpenAI gpt-image-1 API |
| **Floating Furniture** | Low | Refined structural integrity rules forcing floor-plane contact |
| **Hallucination** | Low | Strict "Additive Only" prompt constraints to preserve original architecture |
