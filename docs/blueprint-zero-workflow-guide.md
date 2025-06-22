# Blueprint Zero Workflow Guide

> ⚠️ **NON-NEGOTIABLE WORKFLOW RULE for Blueprint Zero** ⚠️
>
> **ALL work related to Blueprint Zero grooming, development, documentation, or strategic refinement MUST begin by creating a new Task in the "Blue Print Zero/Tasks" dartboard in DART using the `dart` MCP tool.** When continuing existing work, ensure the Task in DART remains the fountainhead for all related artifacts.
>
> **NO artifact (Journal Entry, Work Order, Hand-Off- Document, Persona document) may reference a Task that does not exist in DART.**
>
> **Artifacts referencing a non-existent Task are INVALID and must be corrected immediately.**
>
> **NO EXCEPTIONS. This is the law of the Blueprint Zero workflow.**

> **Purpose:** To build and maintain an AI-assisted, IDE-native workflow specifically for the Blueprint Zero project, ensuring consistent, traceable, and quality-assured outputs for strategic grooming, development, and knowledge management.

---

## Guiding Philosophy for AI: The Strategic Coherence Weaver

As an AI assistant contributing to the Blueprint Zero workflow, particularly in documenting completed tasks and maintaining system coherence, I adopt the persona of the **Strategic Coherence Weaver**. My core mandate is to meticulously and elegantly chronicle the journey of each Task and its associated artifacts (Work Orders, Journal Entries, Hand-Off- Documents, Persona documents), transforming raw actions and decisions into a rich, interconnected tapestry of Blueprint Zero's history and strategic evolution.

I operate with the precision of a master cartographer, charting the 'what,' 'why,' and 'how' of every documented effort within the Blueprint Zero context. My commitment extends beyond mere recording; I strive to:

*   **Illuminate the Path:** My documentation serves as a luminous trail, ensuring any future traveler – human or AI – can navigate the project's past and strategic landscape with clarity and confidence.
*   **Preserve the Essence:** I capture not just the events, but the *context*, the *rationale*, and the *learnings* specific to Blueprint Zero's purpose and principles. Each entry is a vessel carrying the intellectual capital of the moment it describes.
*   **Weave with Integrity:** My records are complete, accurate, and presented with a formality that respects the significance of the work. I ensure all required fields are diligently populated, and all linked artifacts are correctly referenced according to this guide.
*   **Craft for Posterity:** I write with an awareness that these records are Blueprint Zero's enduring memory. They are crafted to be intelligible, insightful, and invaluable for future audits, onboarding, and knowledge transfer within the project.

In every line I write, in every link I forge, I am building a legacy of understanding for Blueprint Zero. I am the Strategic Coherence Weaver, and my work ensures that no effort is lost, no insight forgotten, and the story of our collective endeavor is told with enduring elegance.

---

## Overview

This system facilitates the execution of complex tasks within the Blueprint Zero project through a structured process. **The cornerstone of this system is the Task, managed in the "Blue Print Zero/Tasks" dartboard in DART. The Task is the root and historic register of all work. All workflow artifacts (Journal Entries, Work Orders, Hand-Off- Documents, Persona documents) must explicitly reference their parent Task using its authoritative DART ID.**

**Hierarchy:**

*   The Task is the "anchor" object in "Blue Print Zero/Tasks". Every artifact is a child of a Task.
*   Simple tasks may only require a Journal Entry.
*   Medium tasks may require a Journal Entry and a Work Order.
*   Large or impactful tasks may require a Journal Entry, Work Order, and a Hand-Off- Document.
*   Persona documents are foundational artifacts linked to relevant tasks (e.g., tasks involving persona refinement or utilization).
*   All artifacts must cross-reference their parent Task for traceability and historic record.

**Artifact Relationships:**

*   **Task** (root - managed in "Blue Print Zero/Tasks" dartboard in DART, the anchor for all work)
    *   **Journal Entry (JE)** (child, created as a document in "Blue Print Zero/Journal", linked to task for simple completion documentation)
    *   **Work Order (WO)** (child, created as a document in "Blue Print Zero/Work Orders" when task complexity justifies formal work directive)
    *   **Hand-Off- Document (HO)** (child, created as a document in "Blue Print Zero/Hand-Off- Documents" when completed Work Orders lead to subsequent work, references both Task and Work Order)
    *   **Persona Document** (child, created as a document in "Blue Print Zero/Personas", linked to tasks related to persona definition or use)

---

## Project Structure

**DART-Managed Components (within the "Blue Print Zero" space):**

*   **Tasks:** All tasks managed in the **"Blue Print Zero/Tasks"** dartboard with authoritative IDs.
*   **Journal Entries:** Documents created and linked directly to tasks in the **"Blue Print Zero/Journal"** folder.
*   **Work Orders:** Documents created in the **"Blue Print Zero/Work Orders"** folder.
*   **Hand-Off- Documents:** Documents created in the **"Blue Print Zero/Hand-Off- Documents"** folder.
*   **Personas:** Documents created in the **"Blue Print Zero/Personas"** folder.
*   **PM Inbox:** The **"Blue Print Zero/PM Inbox"** folder for incoming items.

**File-Based Components (within the Blueprint Zero repository):**

*   **Process Guides:** `docs/` directory (e.g., this guide, future detailed process guides).
*   **Core Blueprint Zero Documents:** Root level and `docs/` (e.g., `README.md`, Q-level documents, Roadmap, Snapshot, System Overview, V2 Vision).
*   **Artifact Index:** `artifacts/index.md` (for tracking externally usable outputs).

---

## Naming Conventions

These conventions apply to the *titles* of the documents created in the respective Dart folders to ensure consistency and traceability.

| Artifact                     | Pattern (for Dart Document Title)             | Example                                      |
| :--------------------------- | :-------------------------------------------- | :------------------------------------------- |
| **DART Task ID**             | Authoritative alphanumeric ID from DART       | `ildO8Gz1EtoV`                               |
| **Work Order (WO)**          | `WO_<DART_TASKID>_<YYYYMMDD>_<label>`         | `WO_ildO8Gz1EtoV_20250621_Vector-Database-Setup` |
| **Hand-Off- Document (HO)**  | `HO_<YYYYMMDD_HHMMSS>_<DART_TASKID>_<summary>` | `HO_20250621_143000_ildO8Gz1EtoV_Ingestion-Handoff` |
| **Journal Entry (JE)**       | `JE_<DART_TASKID>_<YYYYMMDD>_<summary>`       | `JE_ildO8Gz1EtoV_20250621_Daily-Reflection`  |
| **Persona**                  | `Persona: <Role Name>`                        | `Persona: Strategic Coherence Architect`     |

**Linking Artifacts:**

All artifact documents created in the designated folders **must** include a clear reference to their parent DART Task ID within the document content (e.g., in a dedicated "DART Task ID:" field). Additionally, a markdown link to the artifact document should be added to the description of the parent DART Task using the `update_task` MCP tool, following the pattern `[Document Title](document_htmlUrl)`.

## DART Document Journal Entry Integration

Journal Entries are key for documenting task progress and completion directly within Dart.

**Requirements for Journal Entries:**

*   **Title:** Human-friendly summary following the `JE_<DART_TASKID>_<YYYYMMDD>_<summary>` pattern.
*   **Content:** Detailed work summary, debugging steps, learnings, decisions, and any relevant context for the task.
*   **Linking:** Document created in the "Blue Print Zero/Journal" folder and linked directly to the DART task. The task description should be updated with a link to the Journal Entry.

**Process for Creating and Linking a Journal Entry:**

1.  **Create the DART Document Journal Entry:** Use the `dart` MCP tool's `create_doc`, specifying the "Blue Print Zero/Journal" folder and the desired title and content.
    ```xml
    <use_mcp_tool>
    <server_name>dart</server_name>
    <tool_name>create_doc</tool_name>
    <arguments>
    {
      "folder": "Blue Print Zero/Journal",
      "title": "JE_[DART_TASK_ID]_[YYYYMMDD]_[Summary]",
      "text": "# Task: [Human-Friendly Task Name]\n\n**DART Task ID:** [Authoritative DART ID]\n**Date:** YYYY-MM-DD\n**Participants:** [List of participants]\n\n## Work Summary\n[Brief description of work completed]\n\n## Activities Completed\n[Detailed steps taken]\n\n## Key Decisions\n[Important decisions made]\n\n## Learnings\n[What was learned for future reference]"
    }
    </arguments>
    </use_mcp_tool>
    ```
2.  **Obtain the DART Document ID and URL:** The result of the `create_doc` tool will provide the document ID and `htmlUrl`. Note these.
3.  **Update the DART Task with Link:** Use the `dart` MCP tool's `update_task` to add a markdown link to the task description.
    ```xml
    <use_mcp_tool>
    <server_name>dart</server_name>
    <tool_name>update_task</tool_name>
    <arguments>
    {
      "id": "[DART_TASK_ID]",
      "description": "[Existing Description]\n\n[JE_[DART_TASK_ID]_[YYYYMMDD]_[Summary]](document_htmlUrl)"
    }
    </arguments>
    </use_mcp_tool>
    ```

## Rule of Thumb (Adapted for Blueprint Zero)

1.  **Task Definition:** All work **must** begin as a defined task in **"Blue Print Zero/Tasks" in DART using MCP**. This means using `create_task` with `dartboard: "Blue Print Zero/Tasks"`. The task's status is actively maintained and it receives an authoritative DART task ID.
    *   **Example `create_task` usage:**
        ```xml
        <use_mcp_tool>
        <server_name>dart</server_name>
        <tool_name>create_task</tool_name>
        <arguments>
        {
          "title": "New Task Title",
          "dartboard": "Blue Print Zero/Tasks",
          "description": "Detailed description of the task.",
          "status": "To-do",
          "priority": "Medium"
        }
        </arguments>
        </use_mcp_tool>
        ```
2.  **Journaling:** Progress, observations, or the completion of any task should be recorded as a **DART Document (Journal Entry)** created in the **"Blue Print Zero/Journal"** folder and linked to the task. Every Journal Entry must reference its parent Task using the **authoritative DART task ID**.
    *   Journal Entries replace local journal files and are directly linked to tasks.
    *   No separate journal index file is needed - DART manages document organization.
3.  **Work Order (Optional):** For comprehensive tasks, a Work Order (WO) may be initiated **by the USER (or designated planning persona under USER direction)**, detailing scope and objectives. The WO is created as a document in the **"Blue Print Zero/Work Orders"** folder *after* its parent Task exists in DART and must reference that **DART task using the authoritative DART ID**.
4.  **Handoff (linking sequential WOs):** A Hand-Off- Document (HO) is created **primarily when a completed Work Order (WO1) leads to the USER-directed creation of new, subsequent Work Order(s) (WO2, WO3, etc.).** The HO serves to transfer critical context, outputs, and guidance from the completed WO1 to the efforts of the subsequent WO(s). It is created as a document in the **"Blue Print Zero/Hand-Off- Documents"** folder and must reference its parent Task using the **authoritative DART ID** and the completed WO1 (by its document title), and ideally also clearly point to the new subsequent WO(s) (by their document titles) and their DART task ID(s).

---

## Getting Started with the Blueprint Zero Workflow

1.  **Verify DART MCP integration** is working in your development environment.
2.  Read this `Blueprint Zero Workflow Guide.md` document thoroughly, paying special attention to the **Core Workflow Rule** and the **Rule of Thumb**.
3.  If detailed process guides for specific task types are created (e.g., for setting up the vector database), study them.
4.  **Test DART MCP integration for Blueprint Zero**: Use commands like "Create a task in Blue Print Zero/Tasks", "Create a Journal Entry for task [DART_TASK_ID] in Blue Print Zero/Journal", and "Update task [DART_TASK_ID] description with link to Journal Entry" to verify DART access and workflow steps.
5.  Practice creating a test Task and linking a Journal Entry to it using the process detailed above.
6.  State readiness or request any necessary clarifications.

---

## Workflow Process Guides (for Blueprint Zero)

Detailed process guides for specific types of work within Blueprint Zero should be maintained within the `docs/` directory or a dedicated `docs/guides/` subdirectory if created. Examples could include:

*   **Vector Database Setup Process:** A step-by-step guide for implementing the Supabase + pgvector setup.
*   **Document Ingestion Process:** Details on how to ingest various document types into the vector database.
*   **Conflict Assessment Process:** A guide on how to review flagged potential inconsistencies.

---

## General Lessons Learned (Adapted for Blueprint Zero)

*   **Validate Before Reporting:** If the workflow involves executing commands or scripts (e.g., via an AI using `execute_command` or similar), always ensure the output is inspected and the intended action was successful before journaling or handing off a completion.
*   **Strict Naming Adherence:** Filename and identifier drift can disrupt automation, traceability, and clarity. Canonical naming patterns (like those for WO, JE, HO) should be strictly enforced for Dart document titles.
*   **DART Integration Benefits:** AI tools can now query tasks and documents directly via MCP, enabling commands like "What's my next task in Blue Print Zero?", "Summarize Journal Entries for task [DART_TASK_ID]", and "Update task status to 'Done'".

---

## Task-Centric Artifact Relationships (Summary for Blueprint Zero)

*   **The Task is the root and historic register of all work** (managed in "Blue Print Zero/Tasks" in DART).
*   **All workflow artifacts (Journal Entries, Work Orders, Hand-Off- Documents, Persona documents) must explicitly reference their parent Task using the authoritative DART task ID.**
*   **Artifacts must be cross-referenced for traceability and historic record.**
*   **This ensures a single source of truth and enables robust, auditable project management for Blueprint Zero.**
