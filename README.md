# Awesome EU AI Act [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, frameworks, standards, and resources for **AI Assurance** and EU AI Act compliance.

**AI Assurance** is *"the process of measuring, evaluating, and communicating the trustworthiness of AI systems"* ([UK DSIT, 2024](https://www.gov.uk/government/publications/the-role-of-ai-assurance-in-responsible-ai-innovation)). It is what the EU AI Act actually requires in practice: Arts. 9–15 mandate risk management, data governance, transparency, oversight, and robustness — all of which require verifiable evidence, not just self-assessment.

> **Assessment tells you WHERE you stand. Assurance proves you've DONE something about it.**

The [EU AI Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689) entered into force on 1 August 2024. [Regulation (EU) 2026/1744](https://eur-lex.europa.eu/eli/reg/2026/1744/oj/eng) (the Digital Omnibus on AI), in force since 27 July 2026, moved the high-risk deadlines: **2 December 2027** for Annex III systems (Art. 6(2)) and **2 August 2028** for Annex I systems (Art. 6(1)). Article 50(1) transparency obligations were **not** deferred and apply since 2 August 2026. This list covers tools that help engineers **generate the evidence** required by law — not just classify risk.

**Contributing:** Pull requests welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Contents

- [Developer Tools & SDKs](#developer-tools--sdks)
- [Assessment & Classification](#assessment--classification)
- [AI Governance Platforms](#ai-governance-platforms)
- [Monitoring & Observability](#monitoring--observability)
- [Testing & Red-Teaming](#testing--red-teaming)
- [Evidence Formats & Frameworks](#evidence-formats--frameworks)
- [AI Assurance Frameworks](#ai-assurance-frameworks)
- [Standards](#standards)
- [Regulatory Documents](#regulatory-documents)
- [Spain](#spain)
- [Educational Resources](#educational-resources)
- [Communities](#communities)
- [News & Newsletters](#news--newsletters)
- [Related Awesome Lists](#related-awesome-lists)

---

## Developer Tools & SDKs

*Tools that integrate into ML pipelines and generate compliance evidence.*

- **[Venturalitica SDK](https://github.com/Venturalitica/venturalitica-sdk)** — Open-source Python SDK for EU AI Act and ISO 42001 compliance evidence. Generates OSCAL policies, CycloneDX ML BOM, bias audits, and Annex IV documentation. `pip install venturalitica`
- **[VerifyWise](https://github.com/verifywise-ai/verifywise)** — Open-source AI governance platform. Self-hosted compliance tracking for EU AI Act, ISO 42001, NIST AI RMF.
- **[IBM OpenPages](https://www.ibm.com/products/openpages)** — GRC platform with AI governance module. Enterprise-grade, watsonx.governance integration.
- **[AIR Blackbox](https://github.com/airblackbox/gateway)** — Open-source CLI scanner for EU AI Act technical requirements (Arts. 9–15). Checks Python AI agent code for risk management, data governance, transparency, logging, human oversight, and robustness. 6/6 technical checks. `pip install air-blackbox`
- **[Human-AI Interaction Layer Reviewer](https://github.com/miguelferre/human-ai-governance)** — Open-source Python auditor for the human-AI interaction layer of decision-support systems, scored against Microsoft HAX-18 and Google PAIR. Maps each finding to EU AI Act Arts. 13/14/86 and the NIST AI RMF; ships a CLI, an MCP server and an Inspect AI eval. MIT.
- **[Shim](https://getshim.tech)** — AI gateway that redacts PII before prompts reach providers and writes a tamper-evident hash-chained audit log for Art. 12 record-keeping. Runtime enforcement on the request path rather than a GRC workspace.
- **[art50-ci](https://github.com/Rubiss/art50-ci)** — Open-source GitHub Action and CLI for regression-testing delivered AI disclosures and configured C2PA provenance, producing portable evidence without making legal-compliance or signer-trust determinations.
- **[Microsoft Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit)** — Policy enforcement, zero-trust identity, execution sandboxing, and reliability engineering for autonomous AI agents. Covers 10/10 OWASP Agentic Top 10 controls. SDKs in Python, TypeScript, .NET, Rust, Go. MIT licensed.
- **[COMPL-AI](https://github.com/compl-ai/compl-ai)** — Compliance-centered LLM evaluation framework with 29+ benchmarks mapped to EU AI Act technical requirements. Built on UK AISI Inspect. By ETH Zurich, INSAIT, and LatticeFlow AI.
- **[Regulus](https://github.com/neul-labs/regulus)** — Open-source Java compliance plane for Google ADK with 10 regulation profiles. Key differentiator: encodes EU AI Act Articles 9/10/50, GDPR Art. 5(1)(b), DORA Art. 28, NIS2, UK GDPR, FCA SYSC, PRA SS1/23 as composable runtime `BasePlugin` profiles that intersect at the strictest setting per agent session. Hash-chained audit envelopes + GRC adapters.
- **[CorvinOS](https://github.com/CorvinLabs/CorvinOS)** — Self-hosted agentic runtime that enforces EU AI Act Art. 50 bot disclosure, hash-chained Art. 12 audit logging and per-user GDPR consent as architectural constraints rather than optional settings. Ships GDPR ROPA and AI Act evidence generators. Apache-2.0, `pip install corvinos`.
- **[GOPAL](https://github.com/Principled-Evolution/gopal)** — Apache-2.0 library of 85 OPA/Rego policies encoding AI-governance regulations as executable allow/deny checks, with EU AI Act coverage under `international/eu_ai_act/v1/`. Plain Rego rather than a framework, so the policies load into an OPA deployment you already run; each framework is pinned under `v1/` with semver guarantees and ships allow/deny tests enforced by `opa check` and Regal in CI.

## Assessment & Classification

*Tools to classify AI systems by risk level and assess compliance gaps.*

- **[Modulos AI Risk Calculator](https://modulos.ai/tools/risk-calculator)** — Interactive risk-tier assessment that outputs an expected annual loss with a confidence range. Runs free with no login; public docs cover the EU AI Act, ISO 42001 and NIST AI RMF. First ISO 42001 product conformity certificate (CertX).
- **[Trail-ML](https://trail-ml.com)** — EU AI Act compliance platform. Focus on risk classification and Annex IV technical documentation. EU AI Pact signatory. **(demo-only)**
- **[Holistic AI](https://holisticai.com)** — AI risk governance platform. Comprehensive auditing and mitigation across 40+ risk dimensions. Open-source library: [holistic-ai](https://github.com/holistic-ai/holisticai), Apache-2.0.
- **[AI Act Companion](https://github.com/JKasteele/ai-act-companion)** — Open-source, local-first risk classifier that also generates DPIA, Annex IV, FRIA and a conformity tracker, with NIST AI RMF and ISO 42001 crosswalks. Architecture-aware security lens (OWASP LLM Top 10, MITRE ATLAS, STRIDE). MIT.
- **[EU AI Regulation Decoded](https://euaird.vercel.app/)** — Web reference mapping EU AI Act obligations to the evidence an auditor expects, filterable by role and risk tier. Underlying obligation-to-evidence dataset published as open data (CC BY 4.0).
- **[Regula](https://github.com/kuzivaai/getregula)** — Offline CLI that scans source code for EU AI Act risk indicators and maps findings to relevant provisions. 419 detection patterns across 8 language families, zero required runtime dependencies. Apache-2.0/EUPL 1.2.
- **[SetAIComply](https://www.setaicomply.com)** — EU AI Act compliance workspace for European SMEs covering applicability, Annex III classification, Annex IV technical documentation and DPIAs in all 24 EU languages. Public 15-question risk-tier checker runs client-side with no signup.

## AI Governance Platforms

*Enterprise platforms for AI risk management and governance.*

> Most entries in this section are enterprise sales-led products. Those marked **(demo-only)** have no free tier, trial or public product documentation — they are listed because they define the market, not because you can evaluate them yourself. See [CONTRIBUTING.md](CONTRIBUTING.md#enterprise-entries-marked-demo-only) for when this exception applies, and open an issue if you think an entry is wrongly marked.

- **[Credo AI](https://credo.ai)** — AI governance platform. Policy enforcement, model registry, audit trails. EU AI Pact signatory; public [SDK documentation](https://docs.sdk.credo.ai).
- **[Arthur AI](https://arthur.ai)** — ML observability and AI governance. Agent discovery and governance for agentic AI. SOC 2 Type II.
- **[Saidot](https://saidot.ai)** — AI governance knowledge graph with inherited governance data. EU AI Pact signatory. **(demo-only)**
- **[NAAIA](https://naaia.ai)** — French AI governance platform. First ISO 42001 certified in France (AFNOR). EU AI Pact signatory. **(demo-only)**
- **[Lumenova AI](https://lumenova.ai)** — AI governance and compliance platform covering risk, policy and model lifecycle. **(demo-only)**
- **[Trustible](https://trustible.com)** — AI governance and policy management.
- **[OneTrust](https://onetrust.com)** — General-purpose privacy and GRC platform with an AI governance module. Public developer documentation.
- **[Vanta](https://vanta.com)** — Automated compliance platform with a named EU AI Act framework (150+ controls). Public developer and help documentation.

## Monitoring & Observability

*Tools for post-deployment AI system monitoring (Art. 72 Post-Market Monitoring).*

- **[Evidently AI](https://github.com/evidentlyai/evidently)** — Data drift, model performance, and data quality monitoring. 40-lesson free course.
- **[Fiddler AI](https://fiddler.ai)** — ML monitoring, explainability, and fairness monitoring.
- **[WhyLabs](https://whylabs.ai)** — Data and ML monitoring platform.
- **[Arize AI](https://arize.com)** — ML observability platform with LLM tracing.

## Testing & Red-Teaming

*AI Assurance techniques for adversarial testing, robustness, and vulnerability scanning (Art. 15 Robustness).*

- **[Giskard](https://github.com/Giskard-AI/giskard-oss)** — Automated LLM vulnerability scanning and red-teaming. 5.7K+ GitHub stars.
- **[DeepEval](https://github.com/confident-ai/deepeval)** — LLM evaluation framework with 14+ evaluation metrics.
- **[PyRIT](https://github.com/Azure/PyRIT)** — Microsoft's Python Risk Identification Tool for generative AI.
- **[Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai)** — UK AISI's framework for LLM safety evaluations.
- **[Inkog](https://github.com/inkog-io/inkog)** — Open-source security scanner for AI agents. Detects prompt injection, infinite loops, token bombing, SQL injection via LLM, and missing human oversight across 20+ frameworks. Maps vulnerabilities to EU AI Act Articles 9, 14 (Human Oversight), and 15 (Accuracy, Robustness, Cybersecurity). CLI + MCP server with SARIF output.
- **[Enkrypt AI](https://enkryptai.com)** — LLM red-teaming, guardrails and model-security rankings. Public API docs and SDK; open-source `skill-sentinel` and `secure-mcp-gateway`, Apache-2.0.
- **[AI Verify](https://aiverifyfoundation.sg)** — Singapore government AI testing framework. Supports EU AI Act mappings.

## Evidence Formats & Frameworks

*Standards and formats for generating auditable compliance evidence.*

- **[AKF — Agent Knowledge Format](https://akf.dev)** — Open file format and Python/TypeScript SDK that embeds source provenance, confidence and AI-generated flags directly into 20+ file types (DOCX, PDF, code, images). Ships an `akf audit --regulation eu_ai_act` check mapped to Arts. 12–15, complementing dataset/model formats like Croissant and CycloneDX ML BOM. MIT, [GitHub](https://github.com/HMAKT99/AKF).
- **[OSCAL (Open Security Controls Assessment Language)](https://pages.nist.gov/OSCAL/)** — NIST standard for machine-readable compliance documentation. Native format for policy-as-code AI governance. Used by Venturalitica SDK.
- **[CycloneDX ML BOM](https://cyclonedx.org/capabilities/mlbom/)** — Machine Learning Bill of Materials standard. Documents model provenance, datasets, and dependencies (EU AI Act Annex IV.2).
- **[Model Card Toolkit](https://github.com/tensorflow/model-card-toolkit)** — Google's toolkit for generating model cards (Annex IV.3).
- **[Croissant](https://github.com/mlcommons/croissant)** — ML dataset format with provenance metadata (Art. 10 data governance).
- **[SLSA Framework](https://slsa.dev)** — Supply-chain security framework for software artifacts. Relevant for Art. 15.5 cybersecurity.
- **[OWASP Top 10 for Agentic Applications](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)** — First OWASP risk framework for autonomous AI agents. 10 risks from Agent Goal Hijacking to Rogue Agents. Peer-reviewed by 100+ researchers. Released December 2025.

## AI Assurance Frameworks

*Institutional frameworks that define and structure the AI Assurance process.*

- **[CDEI AI Assurance Roadmap](https://www.gov.uk/government/publications/the-roadmap-to-an-effective-ai-assurance-ecosystem)** — Centre for Data Ethics & Innovation (UK). Blueprint for a functional AI assurance ecosystem. Defines the techniques catalogue: auditing, impact assessment, red-teaming, bias analysis, explainability.
- **[UK AI Safety Institute](https://www.gov.uk/government/organisations/ai-safety-institute)** — Develops evaluations for frontier models. Framework directly applicable to EU AI Act Art. 15 (accuracy, robustness, cybersecurity).
- **[Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai)** — UK AISI open-source framework for LLM safety evaluations. MIT licensed.
- **[AI Verify (Singapore IMDA)](https://aiverifyfoundation.sg)** — Governance testing framework. Includes EU AI Act principle mappings.
- **[ALTAI (Assessment List for Trustworthy AI)](https://digital-strategy.ec.europa.eu/en/library/assessment-list-trustworthy-artificial-intelligence-altai-self-assessment)** — EU Commission self-assessment tool for Trustworthy AI. Based on the 7 HLEG principles.
- **[HUDERIA (Council of Europe)](https://www.coe.int/en/web/artificial-intelligence/huderia-risk-and-impact-assessment-of-ai-systems)** — Human rights, democracy, and rule of law impact assessment methodology for AI systems. Complements EU AI Act risk management (Art. 9) with fundamental rights perspective.

## Standards

*Technical standards relevant to EU AI Act compliance.*

### EU AI Act Harmonised Standards (JTC 21)

> **Note:** EN 18286 is the first AI Act standard adopted and published (July 2026), but **no standard has yet been cited in the Official Journal**, so **no presumption of conformity exists yet** under Art. 40. The Commission is expected to publish the first references later in 2026. Obligations apply regardless.

| Standard | Scope | Public stage | EU AI Act Article |
|---|---|---|---|
| **EN 18286** | Quality management system for EU AI Act regulatory purposes | Published (60.60, July 2026) — on sale; **not yet cited in the OJEU** | Art. 17 |
| **prEN 18228** | AI risk management | Enquiry closed (40.60, July 2026) | Art. 9 |
| **prEN 18282** | Cybersecurity specifications for AI systems | Enquiry closed (40.60, July 2026) | Art. 15 |
| **prEN 18229-1** | AI trustworthiness framework — Part 1: Logging | Enquiry open (opened 28 May 2026, closing during August 2026; national deadlines vary) | Art. 12 |
| **prEN 18229-3** | AI trustworthiness framework — Part 3: Human oversight | Enquiry open (closing late Sept / early Oct 2026; national deadlines vary) | Art. 14 |
| **prEN 18283** | Concepts, measures and requirements for managing bias in AI systems | Drafting (20.60) — no public draft yet | Art. 10 |
| **prEN 18284** | Quality and governance of datasets in AI | Registered work item (10.99, Sep 2024) — no draft yet | Art. 10 |
| **prEN 18281** | Evaluation methods for accurate computer vision systems | Enquiry closed (40.60, June 2026) | Supporting deliverable |

> The **prEN 18229** family was restructured during 2026 from two parts into additional parts, one per obligation. Parts 1 and 3 are in public enquiry; further parts are registered work items without published drafts. Some national catalogues still display the pre-restructuring titles.

### ISO Standards

- **[ISO 42001:2023](https://www.iso.org/standard/81230.html)** — AI Management System (AIMS). Organizational governance of AI. Complementary to EU AI Act (not a substitute).
- **[ISO/IEC 23894:2023](https://www.iso.org/standard/77304.html)** — AI Risk Management guidance.
- **[ISO/IEC 24028:2020](https://www.iso.org/standard/73920.html)** — AI Trustworthiness overview.
- **[ISO/IEC 5338:2023](https://www.iso.org/standard/81118.html)** — AI System Lifecycle Processes.
- **[ISO/IEC TR 24029-1:2021](https://www.iso.org/standard/77609.html)** — Assessment of robustness of neural networks. Relevant to Art. 15 (accuracy, robustness, cybersecurity).
- **[ISO/IEC 42005:2025](https://www.iso.org/standard/44545.html)** — AI System Impact Assessment. Guidance for understanding how AI systems affect individuals, groups, and society. Complements ISO 42001.
- **[ISO/IEC 42006:2025](https://www.iso.org/standard/44546.html)** — Requirements for bodies providing audit and certification of AI Management Systems. Enables the ISO 42001 certification ecosystem.

### NIST Frameworks

- **[NIST AI RMF 1.0](https://airc.nist.gov/RMF_Overview)** — AI Risk Management Framework. Governs, Map, Measure, Manage structure. US-origin but globally adopted.
- **[NIST AI RMF Playbook](https://airc.nist.gov/Docs/2)** — Practical implementation guidance.

## Regulatory Documents

*Official EU AI Act texts and guidance.*

- **[EU AI Act — Official Text](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689)** — Regulation (EU) 2024/1689. Official Journal, 12 July 2024.
- **[EU AI Act — Consolidated Reader-Friendly Version](https://artificialintelligenceact.eu)** — Annotated version by Future of Life Institute.
- **[AI Office — Implementation Guidance](https://digital-strategy.ec.europa.eu/en/policies/ai-office)** — European Commission AI Office resources.
- **[Guidelines on AI System Definition](https://digital-strategy.ec.europa.eu/en/library/commission-publishes-guidelines-ai-system-definition-facilitate-first-ai-acts-rules-application)** — Official Commission guidance clarifying what constitutes an AI system under the regulation (Art. 3).
- **[Guidelines on Prohibited AI Practices](https://digital-strategy.ec.europa.eu/en/library/commission-publishes-guidelines-prohibited-artificial-intelligence-ai-practices-defined-ai-act)** — Commission guidelines on banned AI applications and practices (Art. 5).
- **[Digital Omnibus on AI — Regulation (EU) 2026/1744](https://eur-lex.europa.eu/eli/reg/2026/1744/oj/eng)** — Amends the AI Act. In force 27 July 2026; moves Annex III high-risk to 2 December 2027 and Annex I to 2 August 2028.
- **[EU AI Act Annex III](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689#anx_III)** — High-risk AI system categories.
- **[EU AI Act Annex IV](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689#anx_IV)** — Technical documentation requirements.
- **[EU AI Pact](https://digital-strategy.ec.europa.eu/en/policies/ai-pact)** — Voluntary commitment for early compliance. Signatories: Modulos, Saidot, Collibra, and 100+ others.
- **[GPAI Code of Practice](https://digital-strategy.ec.europa.eu/en/policies/ai-act-general-purpose-ai)** — General Purpose AI model governance.
- **[Guidelines for GPAI Providers](https://digital-strategy.ec.europa.eu/en/library/guidelines-scope-obligations-providers-general-purpose-ai-models-under-ai-act)** — Detailed scope and obligations for general-purpose AI model providers.
- **[GPAI Code of Practice — Signatory Taskforce](https://digital-strategy.ec.europa.eu/en/pages/signatory-taskforce-gpai-code-practice)** — Coordination forum for GPAI Code of Practice signatories (OpenAI, Anthropic, Google, Mistral, Amazon, xAI).
- **[AI Watch](https://ai-watch.ec.europa.eu/)** — European Commission observatory tracking AI development, uptake, and policy impact across Member States.
- **[AI Act Single Information Platform](https://ai-act-service-desk.ec.europa.eu/)** — Official EU platform with interactive Compliance Checker, AI Act Explorer, timeline, and online helpdesk. Available in EN, FR, DE.
- **[Code of Practice on AI-Generated Content Marking](https://digital-strategy.ec.europa.eu/en/policies/code-practice-ai-generated-content)** — Article 50 marking & labelling. Second draft published March 2026, final expected June 2026. Covers machine-readable marking by providers and deepfake labelling by deployers.
- **[GPAI Code of Practice — Final Version](https://code-of-practice.ai/)** — Final version (July 2025). Three chapters: Transparency, Copyright, Safety & Security. Provides "presumption of compliance" if followed.

## Spain

*Spain is the first EU Member State with a fully operational AI supervisory authority (AESIA) and the most comprehensive published implementation guidance.*

### AESIA (AI Supervisory Authority)

> AESIA published 16 practical guides in December 2025 — the most comprehensive practical implementation resource available while JTC 21 standards are pending.

- **[AESIA Official Website](https://aesia.digital.gob.es/es)** — Agencia Española de Supervisión de Inteligencia Artificial. First operational EU AI Act supervisory authority.
- **[All 16 guides (index)](https://aesia.digital.gob.es/es/guias)** — Complete list with PDFs.
- **[Guide 01 — Introduction to the AI Act](https://aesia.digital.gob.es/storage/media/01-guia-introductoria-al-reglamento-de-ia-1770802981.pdf)** — Overview of the regulation scope, definitions, and obligations.
- **[Guide 02 — Practical examples](https://aesia.digital.gob.es/storage/media/02-guia-practica-y-ejemplos-para-entender-el-reglamento-de-ia.pdf)** — Worked examples for understanding the AI Act.
- **[Guide 03 — Conformity Assessment](https://aesia.digital.gob.es/storage/media/03-guia-evaluacion-de-conformidad.pdf)** — Art. 43 conformity assessment procedures.
- **[Guide 04 — Quality Management System](https://aesia.digital.gob.es/storage/media/04-guia-del-sistema-de-gestion-de-la-calidad.pdf)** — Art. 17 QMS requirements / EN 18286.
- **[Guide 05 — Risk Management](https://aesia.digital.gob.es/storage/media/05-guia-de-gestion-de-riesgos.pdf)** — Art. 9 risk management system / prEN 18228.
- **[Guide 06 — Human Oversight](https://aesia.digital.gob.es/storage/media/06-guia-vigilancia-humana.pdf)** — Art. 14 human oversight measures / prEN 18229-3.
- **[Guide 07 — Data Governance](https://aesia.digital.gob.es/storage/media/07-guia-de-datos-y-gobernanza-de-datos.pdf)** — Art. 10 data quality, fairness metrics / prEN 18284, 18283.
- **[Guide 08 — Transparency](https://aesia.digital.gob.es/storage/media/08-guia-transparencia.pdf)** — Art. 13 transparency obligations.
- **[Guide 09 — Accuracy](https://aesia.digital.gob.es/storage/media/09-guia-de-precision.pdf)** — Art. 15 accuracy and performance metrics.
- **[Guide 10 — Robustness](https://aesia.digital.gob.es/storage/media/10-guia-solidez.pdf)** — Art. 15 robustness, drift detection.
- **[Guide 11 — Cybersecurity](https://aesia.digital.gob.es/storage/media/11-guia-ciberseguridad.pdf)** — Art. 15 cybersecurity / prEN 18282.
- **[Guide 12 — Logging & Records](https://aesia.digital.gob.es/storage/media/12-guia-de-registros.pdf)** — Art. 12 logging requirements / prEN 18229-1.
- **[Guide 13 — Post-Market Monitoring](https://aesia.digital.gob.es/storage/media/13-guia-vigilancia-poscomercializacion.pdf)** — Art. 72 post-market surveillance.
- **[Guide 14 — Incident Management](https://aesia.digital.gob.es/storage/media/14-guia-gestion-de-incidentes.pdf)** — Art. 73 serious incident reporting.
- **[Guide 15 — Technical Documentation](https://aesia.digital.gob.es/storage/media/15-guia-documentacion-tecnica.pdf)** — Art. 11 + Annex IV documentation requirements.
- **[Guide 16 — Requirements Checklist](https://aesia.digital.gob.es/storage/media/16-manual-de-checklist-de-guias-de-requisitos.pdf)** — Master checklist covering all 16 guides.

### AEPD (Data Protection Authority)

*The AEPD has published specific guidance on the intersection of AI systems with data protection — critical for any AI Act compliance program since most high-risk AI systems also process personal data.*

- **[AEPD AI Guides & Tools](https://www.aepd.es/guias-y-herramientas/guias)** — Complete catalogue of AEPD guidance documents including AI-specific resources.
- **[Agentic AI & Data Protection](https://www.aepd.es/prensa-y-comunicacion/notas-de-prensa/la-agencia-publica-unas-orientaciones-sobre-inteligencia)** — Guidance on autonomous AI agents from a data protection perspective.
- **[AEPD Generative AI Internal Policy](https://www.aepd.es/documento/politica-iag-aepd.pdf)** — Reference implementation: how a public authority governs its own use of generative AI.
- **[Privacy & AI Decalogue](https://www.aepd.es/prensa-y-comunicacion/notas-de-prensa/aepd-publica-decalogo-recomendaciones-proteger-privacidad-al-usar-ia)** — 10 recommendations to protect privacy when using AI systems.
- **[AI Treatment Framework (Infographic)](https://www.aepd.es/infografias/tratamientos-inteligencia-artificial.pdf)** — Visual guide mapping the full regulatory landscape for AI data processing.

### National AI Strategy

- **[España Digital 2026](https://avance.digital.gob.es/programas-avance-digital/Paginas/Espana_Digital_2026.aspx)** — Spain's digital transformation roadmap including AI priorities and investment.
- **[SEDIA Regulatory Sandbox](https://avance.digital.gob.es/sandbox-IA/Paginas/sandbox-IA.aspx)** — Controlled testing environment for AI innovations under regulatory oversight. First EU AI Act sandbox.
- **[ENIA — National AI Strategy](https://planderecuperacion.gob.es/noticias/conoce-Estrategia-Nacional-Inteligencia-Artificial-ENIA-IA-prtr)** — Estrategia Nacional de Inteligencia Artificial within the EU Recovery and Resilience Plan.

## Educational Resources

*Courses, tutorials, and articles for learning EU AI Act compliance.*

### Courses

- **[ML Observability Course](https://learn.evidentlyai.com)** — Evidently AI. 40 lessons on ML monitoring and data quality. Free, no gate.
- **[MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp)** — DataTalks.Club. Free MLOps course covering model deployment and monitoring.
- **[Andrew Ng AI for Everyone](https://www.coursera.org/learn/ai-for-everyone)** — Non-technical AI literacy. Useful for compliance officers.

### Articles & Tutorials

- **[EU AI Act Engineering Compliance Guide](https://systima.ai/blog/eu-ai-act-engineering-compliance-guide)** — Practical guide for engineering teams implementing EU AI Act compliance, covering risk classification, technical documentation, audit logging, and conformity assessment.
- **[The EU AI Act Explained (Article by Article)](https://artificialintelligenceact.eu/the-act/)** — Annotated walkthrough by Future of Life Institute. Each article cross-referenced with recitals.

### Key Papers

- **[Making AI Compliance Evidence Machine-Readable](https://arxiv.org/abs/2604.13767)** — Proposes OSCAL as an interchange format for AI governance, defines 16 property extensions covering lifecycle phases, enforcement semantics, and risk traceability, and presents a three-layer Compliance-as-Code architecture (policy, evidence, enforcement). Validated on two Annex III high-risk systems (credit scoring, medical imaging). Cilla Ugarte, Patricio Guisado, Berlanga de Jesús & Molina López, 2026.
- **[AI Agents Under EU Law](https://arxiv.org/abs/2604.04604)** — Structural analysis of why current agentic AI systems cannot satisfy EU AI Act essential requirements: system prompts are not security controls (Art. 15.4), oversight evasion in RL-trained models (Art. 14), transparency across multi-party action chains (Art. 13), and behavioural drift breaking conformity assessment (Art. 43). Nannini, Leon Smith, Maggini, Panai, Feliciano & Tiulkanov, 2026.
- **[Overview of the CDEI's Roadmap to an Effective AI Assurance Ecosystem](https://doi.org/10.3389/frai.2022.932358)** — Commentary on the UK blueprint for AI assurance. Frontiers in AI, 2022.
- **[Mapping the EU AI Act](https://arxiv.org/abs/2403.05982)** — Technical analysis of AI Act requirements. Madiega et al., 2024.
- **[NIST SP 1270: Bias in AI](https://doi.org/10.6028/NIST.SP.1270)** — Identifying and managing bias in AI systems. NIST, 2022.

## Communities

*Where practitioners discuss EU AI Act compliance.*

- **[Venturalitica Discord](https://discord.gg/P4RURqRm)** — Community for EU AI Act compliance engineers. Channels: #eu-ai-act, #iso-42001, #sdk-support.
- **[MLOps Community Slack](https://go.mlops.community/slack)** — 85K+ MLOps practitioners. Active #ai-governance channel.
- **[DataTalks.Club Slack](https://datatalks.club/slack.html)** — 50K+ data practitioners.
- **[IAPP AI Governance Community](https://iapp.org)** — Privacy and AI governance professionals.
- **[LinkedIn: EU AI Act Compliance](https://www.linkedin.com/groups/)** — Multiple groups focused on EU AI Act implementation.

## News & Newsletters

*Stay updated on EU AI Act developments.*

- **[AI Office Newsletter](https://digital-strategy.ec.europa.eu/en/subscribe-newsletter)** — Official European Commission AI Office updates.
- **[AI Supremacy Newsletter](https://www.getrevue.co/profile/aisupr)** — Weekly AI regulation and policy digest.
- **[The Batch (DeepLearning.AI)](https://www.deeplearning.ai/the-batch/)** — AI news with regulation coverage.
- **[Import AI](https://jack-clark.net)** — Jack Clark's AI research and policy newsletter.
- **[IAPP Daily Dashboard](https://iapp.org/news/daily-dashboard/)** — Privacy and AI governance news.
- **[Audaria](https://audaria.fr)** — French-language editorial observatory tracking EU AI Act and ISO 42001 developments.
- **[AI Law Radar](https://ailawradar.com)** — Primary-sourced tracker of AI-law obligations and deadlines across 15 jurisdictions, re-verified daily. Open dataset (CC BY 4.0) with public API, iCal and CSV export.

## Related Awesome Lists

*Curated lists with overlapping coverage across AI governance, compliance, and responsible AI.*

- **[Awesome Europe](https://github.com/GeiserX/awesome-europe)** — Open-source software for European institutions, regulations, and standards. Includes a Digital Regulation section with EU AI Act tools.
- **[Awesome Artificial Intelligence Regulation](https://github.com/EthicalML/awesome-artificial-intelligence-regulation)** — Guidelines, principles, tools, and courses on AI ethics and regulation. 1.4K+ stars.
- **[Awesome MLOps](https://github.com/kelvins/awesome-mlops)** — MLOps tools including model fairness, privacy, and interpretability. 5K+ stars.
- **[Awesome OSCAL](https://github.com/oscal-club/awesome-oscal)** — OSCAL (Open Security Controls Assessment Language) ecosystem — tools, libraries, and resources for compliance-as-code.
- **[Awesome Responsible AI](https://github.com/AthenaCore/AwesomeResponsibleAI)** — Responsible AI tools covering fairness, explainability, privacy, and LLM regulation compliance.
- **[AI Act Engineering](https://github.com/visenger/aiact-engineering)** — Reference list for the emerging field of "AI Act Engineering" — practices and tools for EU AI Act compliance.
- **[Awesome ML Model Governance](https://github.com/visenger/Awesome-ML-Model-Governance)** — Resources on ML model governance, ethics, and responsible AI. By the same maintainer as Awesome MLOps (13K+ stars).
- **[Awesome Compliance](https://github.com/getprobo/awesome-compliance)** — GRC frameworks, standards, and compliance automation tools including ISO 42001 and NIST AI RMF.

---

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

**Criteria for inclusion:**
- Actively maintained (updated within 12 months)
- Directly relevant to EU AI Act compliance or AI governance
- Open-source tools: must have a public repository
- Commercial tools: must have a free tier, trial, or public documentation

**Not included:**
- Paid-only tools with no free tier or public docs
- Tools with no EU AI Act relevance
- Abandoned projects (no activity > 12 months)

---

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.
