---
icon: memo
---

# Constitution

<figure><img src="../.gitbook/assets/constitution picture.png" alt=""><figcaption></figcaption></figure>

The <mark style="color:$primary;">Constitution Module</mark> is the governance interface that facilitates off-chain deliberation, revision, and analytical verification of the Cardano Constitution. It is designed for Advanced Governance Participants (D-Reps, CC members) to engage deeply with the foundational rules, propose sophisticated amendments, and leverage data to ensure constitutional fidelity. The module's focus is on transforming the statutory text into an actionable, traceable, and analyzable governance resource.

***

## <mark style="color:$primary;">Constitution Content and Off-Chain Discussion</mark>

This component serves as the primary workspace for discussing and interacting with the active governance framework. Its focus is on making the Constitution accessible and interactive for amendment planning.

### <mark style="color:$primary;">**Hierarchical**</mark> <mark style="color:$primary;"></mark><mark style="color:$primary;">Display and Rule Access</mark>

The module retrieves all enacted (on-chain) versions of the Constitution. The latest official version is displayed to the user via the Constitutions Content feature. This display utilizes a tree-like, relational structure to logically break down the Constitution into manageable sections and subsections. Clicking on any node in this hierarchy reveals the specific Rules and clauses contained within that section. This presentation format drastically improves navigation and contextual comprehension compared to a monolithic text document.

### <mark style="color:$primary;">Amendment Workflow</mark>

DReps, SPOs  and CCs utilize this module to develop **proposed Amendments** to the Constitution. The module provides a full suite of GovCircle features to accurately define the required change before on-chain submission:

* <mark style="background-color:blue;">**Create, Delete, Update:**</mark> Standard actions for modifying the text or intent of specific rules.
* <mark style="background-color:blue;">**Update (Goal Change/Preservation):**</mark> Specialized update actions to distinguish whether the proposed change alters the fundamental objective of the rule or merely refines the language while preserving the original intent.

{% hint style="info" %}
Goal Preservation Update used when the legal intent remains, but only the specific language requires refinement.
{% endhint %}

### <mark style="color:$primary;">Discussion and Outreach</mark>

To ensure constitutional changes are informed by community consensus, the module integrates dedicated communication channels:

* <mark style="background-color:blue;">Discussion Section:</mark> Provides a dedicated forum for D-Reps to engage directly with the community and their Delegators regarding their amendment proposals and viewpoints.
* <mark style="background-color:blue;">Event Manager Integration:</mark> Representatives can utilize the Event Manager module to share their rationale and gather community feedback on proposed changes via external social networks, logging the discussion within the GovCircle context.

***

## <mark style="color:$primary;">Version History and Amendment Traceability</mark>

Given the text-based nature of the Constitution, maintaining clear version control is a major challenge during voting. This module provides a robust solution to visualize changes across time.

### <mark style="color:$primary;">Interactive Difference Checker</mark>

Unlike standard **`diff checker`** open-source tools or simple version logs (such as those previously found in GovTool) which struggle to accurately display differences when a Constitution's structural integrity is altered, the GovCircle Version History module provides an interactive display of constitutional differences. This display highlights the exact textual changes alongside the specific Amendment Action (e.g., Delete, Edit) that caused the change. This clarity is essential for voters to distinguish exactly what they are approving or rejecting.

### <mark style="color:$primary;">Validity Score and Rule Reliability</mark>

The module automatically calculates and displays the Validity Score for every individual Rule or Section within the Constitution. This score provides participants with a data-driven measure of the section's stability and efficacy over time:

<p align="center"><span class="math">\text{Validity Score} \propto \frac{\text{Actions Prevented} + \text{Actions Passed}}{\text{On-Chain Versions Unchanged}}</span></p>

* <mark style="background-color:blue;">**Actions Prevented:**</mark> The count of proposed governance actions that were blocked because they violated this specific rule.
* <mark style="background-color:blue;">**Actions Passed:**</mark> The count of governance actions that were approved while upholding this specific rule.
* <mark style="background-color:blue;">**Versions Unchanged:**</mark> The number of on-chain constitutional versions in which this rule has remained unaltered.

This automated metric identifies clauses that are robust and critical to the system's function (high score) versus those that are often changed or have little impact (low score).

***

## <mark style="color:$primary;">Action Checker and Constitutional Fidelity</mark>

The Action Checker is a powerful analytical tool designed specifically for the Constitutional Committee (CC) to ensure all on-chain actions comply with the standing law.

### <mark style="color:$primary;">Linking Actions to Rules</mark>

The primary function allows CC members to review proposed on-chain governance actions and check them against the relevant Rules in the Constitution. If a proposed action is found to violate a constitutional principle, the CC can formally link the infringing action to the specific constitutional clause it rejects.

### <mark style="color:$primary;">Reporting and Rule Importance</mark>

While CC rationales often contain this information as simple text, the Action Checker formalizes the process. This linking capability generates valuable reports demonstrating the importance and impact of each constitutional rule. The reports reveal:

* **Vetting Effectiveness:** Which clauses are most frequently used to veto or prevent illegitimate actions.
* **Rule Validation:** The cumulative number of times a rule has been cited to prevent an action, effectively showing its practical validity and necessity within the framework.

This systematic tracking provides crucial data to validate the ongoing importance of every rule in the Constitution, moving beyond qualitative assessment toward quantitative accountability.

## <mark style="color:$primary;">Conclusion: Ensuring Constitutional Fidelity</mark>

The Constitution Module transcends the role of a static legal document, transforming the foundational governance text into a dynamic, data-driven system of accountability and structural stability. By providing advanced tooling for granular amendment management, interactive version traceability, and the automatically calculated Validity Score, the module ensures that constitutional evolution is always deliberate, informed, and transparent. Critically, the Action Checker formalizes the oversight role of the Constitutional Committee by establishing a verifiable link between governance actions and the specific rules they uphold or violate. Ultimately, this module is the guardian of GovCircle's long-term stability, empowering advanced participants to maintain the integrity and relevance of the constitutional framework across all iterations of the decentralized ecosystem.
