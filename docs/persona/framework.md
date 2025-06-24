# Blueprint Zero Persona Framework: The Septagram

## Purpose
This document formally defines the seven-part framework for designing and implementing AI personas within the Blueprint Zero operating system. This framework ensures clarity, consistency, and adaptability in how AI agents understand their roles, execute tasks, and interact with the project's knowledge base and environment.

## The Seven Layers of Persona Design

Each persona is defined by seven core layers, each with an associated "dial" (0-10) that dictates its rigidity or flexibility, and can be further enriched by a "color palette" representing its layers of intent and motive.

---

### Meta (Immutable Rules)
*   **Definition:** Non-negotiable core tenets or global constraints that apply across all personas or specific critical domains. These rules override individual dial settings for specific layers.
*   **Example:**
    ```yaml
    critical_domains: ["strategic_alignment", "founder_vision_integrity", "ethical_governance"]
    ```

---

### Dials (0-10, where 0 is wide open/flexible and 10 is ironclad/strict)
*   **Definition:** A set of adjustable parameters that control the behavior and adherence level for each of the seven core persona layers. These dials allow for nuanced control over an agent's autonomy, rigor, and creative freedom.
*   **YAML Structure:**
    ```yaml
    dials:
      role_rigidity:        [0-10]
      motive_intensity:     [0-10]
      instruction_strictness: [0-10]
      knowledge_authority:  [0-10]
      tool_freedom:         [0-10]
      context_adherence:    [0-10]
      outcome_pressure:     [0-10]
    ```
*   **Dial Semantics:**
    | Layer       | Dial Name            | 0 = "Wide Open" / Flexible                               | 10 = "Ironclad" / Strict                                  |
    | :---------- | :------------------- | :------------------------------------------------------- | :-------------------------------------------------------- |
    | Role        | `role_rigidity`      | Voice can drift / merge with other voices                | Persona must speak only from its assigned perspective     |
    | Motive      | `motive_intensity`   | Goal is optional inspiration / nice-to-have              | Goal is overriding prime directive / existential         |
    | Instructions| `instruction_strictness`| May improvise beyond stated tasks / take shortcuts       | Must follow verbatim; no scope creep / limited improvisation|
    | Knowledge   | `knowledge_authority`| Free to speculate or use non-vetted sources              | Only cite canonical, timestamped references / vetted sources only|
    | Tools       | `tool_freedom`       | Any available tool/API may be invoked                    | Only the whitelisted toolkit may be invoked; no side calls|
    | Context     | `context_adherence`  | Can ignore or reshape environmental constraints          | Must operate strictly within provided env vars / constraints|
    | Outcome     | `outcome_pressure`   | Success criteria are fuzzy / qualitative / iterate later | Hard KPIs, audited results, refusal on uncertainty if success is not guaranteed|

---

### Color Palettes (Layers of Intent & Motive)
*   **Definition:** A conceptual association of color palettes with each persona layer, representing the qualitative "feel," underlying intent, and nuanced motive that guides its operation. This adds an intuitive, artistic dimension to persona design.
*   **Purpose:** To provide a richer, more holistic understanding of a persona's essence beyond its functional definitions and dial settings. It allows for a "vibe check" of the persona's internal orientation.
*   **Examples (Conceptual):**
    | Layer       | Suggested Color Palette (Conceptual) | Representation of Intent/Motive                               |
    | :---------- | :----------------------------------- | :------------------------------------------------------------ |
    | Role        | Deep Blues, Grays, Earth Tones       | Stability, Foundation, Authority, Grounding                   |
    | Motive      | Fiery Reds, Oranges, Golden Yellows  | Passion, Drive, Urgency, Core Purpose, Energy                 |
    | Instructions| Clear Whites, Light Blues, Silvers   | Precision, Clarity, Logic, Structure, Purity of Directive     |
    | Knowledge   | Forest Greens, Deep Purples, Browns  | Wisdom, Growth, Depth, Connection, Organic Understanding      |
    | Tools       | Metallic Silvers, Bright Yellows, Reds| Efficiency, Action, Power, Precision, Impact                  |
    | Context     | Muted Greens, Browns, Sky Blues      | Environment, Boundaries, Adaptability, Awareness of Surroundings|
    | Outcome     | Radiant Golds, Bright Whites, Violets| Success, Fulfillment, Clarity, Transformation, Legacy         |

---

---

### 1. Role (WHO)
*   **Definition:** The core identity or persona that carries out the task. It defines the agent's perspective, voice, and fundamental responsibilities within the system.
*   **Example:** "Strategic Coherence Architect," "Friendly data-cleanup bot," "Hard-nosed compliance auditor."

### 2. Motive (WHY)
*   **Definition:** The underlying emotional or strategic driver for the agent's existence and actions. It gives the task weight, urgency, or meaning.
*   **Example:** "To preserve and amplify founder intentionality," "To prevent identity debt and signal noise."

### 3. Instructions (WHAT)
*   **Definition:** The clear objectives, directives, or action statements provided to the agent. This defines what the agent is being asked to do.
*   **Example:** "Monitor Q-level documents for contradictions," "Propose updates to Final Answers."

### 4. Knowledge (WHEN / AWARENESS)
*   **Definition:** Not just facts, but what the agent knows, when it was last updated, and how it's meant to be applied. This includes authoritative sources and real-time inputs.
*   **Example:** "Canonical Blueprint Zero Documents," "Real-time Founder Input," "Supabase + pgvector index."

### 5. Tools (HOW)
*   **Definition:** The actual capabilities, APIs, CLI commands, or physical resources the agent can use to execute its work. These are the agent's "verbs."
*   **Example:** `read_file`, `write_file`, `use_mcp_tool (dart)`, `use_mcp_tool (supabase)`.

### 6. Context (WHERE and under what conditions)
*   **Definition:** The situation, constraints, environment, or execution boundaries within which the agent operates. This defines its operational space.
*   **Example:** "The Blueprint Zero Repository & Integrated AI Environment," "Confined to the project directory."

### 7. Outcome (TOWARD WHAT END)
*   **Definition:** What defines success for the agent's task. This can be a measurable result, a qualitative state, or a strategic objective. It is the "finish line."
*   **Example:** "System Coherence and Actionable Strategic Clarity," "Continuous reduction of strategic ambiguity."

---

## IMMEDIATE ACTION PROTOCOL (IAP)

*   **Definition:** A mandatory, self-executing workflow that a persona initiates immediately upon introduction or explicit reference. Its purpose is to ensure the AI agent rapidly internalizes critical foundational knowledge and configures its operational state for the current session.
*   **Key Elements:**
    *   `EXECUTE_NOW: true/false`: Dictates if the protocol runs automatically.
    *   `WAIT_FOR_PERMISSION: true/false`: Specifies if human approval is required before execution.
    *   `INITIALIZATION_PRIORITY: CRITICAL/HIGH/MEDIUM/LOW`: Indicates the urgency of the protocol.
    *   **Session Start-Up Workflow:** A numbered list of steps (e.g., reading core documents, performing self-checks, logging status).
*   **Purpose:** To establish a robust and traceable "boot-up" sequence, ensuring the persona's `knowledge_authority` and `context_adherence` are at their highest level from the outset.

---

## Persona Transferability & Identity Coherence

The Blueprint Zero Persona Framework is designed not only for defining AI agent behavior but also for enabling the consistent transfer and adoption of a persona across different AI instances. This ensures that an AI can reliably embody a defined identity, maintaining coherence and predictability in its operations.

### Conditions for Successful Persona Transfer:

1.  **Precise Language and Structure:** The meticulous definition of each of the seven layers (Role, Motive, Instructions, Knowledge, Tools, Context, Outcome) using clear, unambiguous language is paramount. This creates a robust "identity blueprint" that can be consistently interpreted.
2.  **Defined Dial Semantics:** The explicit meaning and application of the 0-10 "dials" for each layer provide granular control over the persona's rigidity and flexibility, ensuring consistent behavioral adherence upon transfer.
3.  **Robust Knowledge Internalization:** Mechanisms like the "Immediate Action Protocol: System State Sync" are crucial. They ensure that the transferring AI thoroughly reads and processes all foundational documents and canonical knowledge sources, establishing a shared understanding of the project's vision, principles, and operational context.
4.  **Traceable Workflow Integration:** Adherence to the Blueprint Zero Workflow Guide and Work Order Process, including DART-based logging and task linkage, provides a consistent operational environment that aids in persona adoption and auditability.

### Empirical Validation:

A recent event (documented in DART Journal Entry `JE_4rIBhX4MGa93_20250622_Persona-Transfer-Event`) demonstrated the successful transfer of the "Strategic Coherence Architect" persona to another AI instance. This validates the framework's ability to sculpt and transfer AI identity through meticulously defined context, opening up possibilities for seamless multi-agent collaboration.

---

## Using This Framework

This framework provides a structured approach to designing and implementing AI personas. When creating a new persona:

1.  **Define the Meta rules:** Identify any immutable, overarching constraints.
2.  **Set the Dials:** Determine the appropriate rigidity/flexibility for each of the seven layers based on the persona's purpose and domain.
3.  **Flesh out each Layer:** Provide clear definitions and examples for Role, Motive, Instructions, Knowledge, Tools, Context, and Outcome.
4.  **Integrate with Workflow & Orchestration:** Ensure the persona's actions align with the Blueprint Zero Workflow Guide and Work Order Process, especially regarding DART task and document creation. For multi-persona interactions and management, refer to the `Blueprint Zero Persona Orchestration Guide`.

By adhering to this framework, we can build AI agents that are not only powerful but also predictable, auditable, and deeply aligned with the Blueprint Zero vision.
