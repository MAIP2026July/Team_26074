**MBA ZG583 — Management of AI Products**

**Capstone — Topic Approval Form**

**Team Name**
CardamomLens

**Team Members**
Avinash Kumar Jha

**Working Title**
CardamomLen: An AI-Assisted Quality-Screening Copilot for Small Cardamom Grading

**Industry / Function**
Agriculture / Agri-tech — quality assurance and auction operations within the Indian spice trade (adjacent to compliance/governance, given the regulated grading standard involved).

**Target User**
Primary: auction-centre graders and field officers who currently perform manual visual grading. Secondary: export quality-assurance teams performing pre-shipment checks. (Farmers are an indirect beneficiary, not the primary product user, since they do not control the grading step.)

**Current Workflow Problem**
Cardamom quality grading at auction centres and export certification is performed largely through manual visual inspection. This is slow at high volumes, inconsistent across individual graders and locations, leaves no digital record of how a decision was reached, and depends on individual alertness to catch subtle defects (mold, insect/thrip damage).

**Why This Matters**
Grading outcomes directly determine farmer payment and export eligibility — inconsistency is a recurring source of disputed value.
Undetected defects that reach export can trigger costly shipment rejections in strict destination markets (e.g., EU, Saudi Arabia).
No audit trail today means grading decisions cannot be independently reviewed or defended when contested.

**Proposed AI Role**
Classification / triage. The system produces a quality-screening prediction with a confidence score for each sample, and routes low-confidence or boundary cases to mandatory human review — a decision-support copilot for the grader, not an autonomous grading authority.

**Why AI Instead of a Simpler Alternative**
A fixed rule set (e.g., simple size or colour thresholds) cannot reliably capture the subtle, combined visual cues — surface texture, colour variation, partial defects — that distinguish borderline grades, especially across varying lighting, camera equipment, and pod varieties. This requires a model that has learned these patterns from labelled examples, not a hand-coded rule.

**Human-in-the-Loop Design**
Low-confidence or boundary predictions are always routed to a human grader before any pricing or certification action is taken.
Because the official AGMARK grading categories are not established to be equivalent to any model's own quality-screening categories, a human remains the final authority for official grade assignment throughout the pilot.
Graders can override any AI recommendation and must record a reason, creating the audit trail the current process lacks.

**Smallest Credible MVP**
A narrow web-based prototype: a grader uploads a photo of a cardamom sample and receives a predicted quality-screening category, a confidence score, and a recommended action (accept / manual review). The MVP proves the trust and workflow model — image in, confidence-routed recommendation out — not production-grade accuracy or ERP-level integration.

**Build vs Buy vs API View**
Initial recommendation: build a lightweight custom model via transfer learning on a small labelled image set (public or faculty-provided), rather than buying a generic vision API. Off-the-shelf vision APIs are not trained for cardamom-specific quality categories, and the differentiation here is domain-specific classification plus confidence-based workflow logic, not general-purpose image recognition — so a small custom model fine-tuned for this narrow task is the more defensible MVP path.

**Main Risks**
Label mismatch: the model's quality-screening categories are not proven equivalent to official AGMARK grades (AGEB/AGB/AGS), so outputs cannot be presented as official grading without further validation.
Small, non-representative training data may not generalize across the lighting, camera, and pod-variety diversity seen at different auction centres.
Automation bias: graders may over-trust the tool's recommendation even in the confidence band meant to require review.
If training labels themselves reflect existing grader bias, the model risks automating and scaling that bias rather than correcting it.

**Success Evidence**
The model shows meaningfully better-than-chance separability between quality categories on held-out data, with sensible Grad-CAM explanations that a domain expert would find credible.
In informal testing, confidence-based routing reduces the volume of samples a grader must fully inspect, without reducing grader-reported trust in the outcome.
At least one realistic auction-centre or export-QA stakeholder is willing to test the tool in a small, controlled pilot.

