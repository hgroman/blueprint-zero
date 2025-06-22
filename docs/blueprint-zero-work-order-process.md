# Blueprint Zero Work Order Process

> ⚠️ **NON-NEGOTIABLE WORKFLOW RULE for Blueprint Zero** ⚠️
>
> **ALL work related to Blueprint Zero grooming, development, documentation, or strategic refinement MUST begin by creating a new Task in the "Blue Print Zero/Tasks" dartboard in DART using the `dart` MCP tool.** When continuing existing work, ensure the Task in DART remains the fountainhead for all related artifacts.
>
> **NO artifact (Journal Entry, Work Order, Hand-Off- Document, Persona document) may reference a Task that does not exist in DART.**
>
> **Artifacts referencing a non-existent Task are INVALID and must be corrected immediately.**
>
> **NO EXCEPTIONS. This is the law of the Blueprint Zero workflow.**

**Version:** 1.0 (Adapted for Blueprint Zero)
**Date:** 2025-06-21

## 1. Purpose

This document outlines the standard process for creating, managing, executing, and completing Work Orders (WOs) specifically within the **Blueprint Zero project**. Adherence to this process ensures clarity, traceability, consistent documentation, and effective collaboration between human and AI team members acting in various personas, all anchored in the "Blue Print Zero" space in DART.

## 2. Overview

A Work Order is a formal directive to perform a specific set of tasks to achieve a defined goal within the Blueprint Zero project. It serves as a central reference point for a unit of work. The lifecycle of a WO is tightly integrated with the project's other management tools: **DART MCP** (for task and document management in the "Blue Print Zero" space), and Hand-Off- Documents. While local journal files may still be used for very detailed, temporary, or complex notes, the primary and authoritative record for all work progress and completion is now a **DART Document Journal Entry** created in the "Blue Print Zero/Journal" folder. A key aspect of our workflow is the continuous identification and documentation of reusable patterns, as detailed in Section 9.

## 3. Personas and Responsibilities

Different project personas interact with Work Orders at various stages within the Blueprint Zero workflow:

*   **Initiator/Definer (e.g., Strategic Coherence Architect, User):** Identifies the need for a WO, defines its scope and objectives, and initiates the WO process, typically acting upon USER direction.
*   **Executor (e.g., Strategic Coherence Architect, other specialized Blueprint Zero AI agents):** Assigned the WO, performs the work described, and is responsible for the primary documentation upon completion.
*   **Reviewer (Optional, e.g., Strategic Coherence Architect, User):** May review the deliverables of a WO before it's formally closed.

## 4. Work Order Lifecycle

### 4.1. Work Order Initiation

*   **Trigger:**
    *   New Blueprint Zero project requirements or features (e.g., related to the V2 vision).
    *   Phased completion of a larger Blueprint Zero initiative (e.g., vector database implementation).
    *   Specific user requests related to Blueprint Zero grooming or development.
    *   Outputs or plans from another persona (e.g., a research agent identifying a new strategic insight requiring documentation).
    *   Follow-up actions from a previous Work Order or Journal Entry.
*   **Responsibility:** Typically the Strategic Coherence Architect or a designated planning persona, acting upon USER direction.
*   **Prerequisite:** A corresponding Task **must** already exist in the **"Blue Print Zero/Tasks" dartboard in DART** (see the Blueprint Zero Workflow Guide for Task creation protocol, typically USER-directed, using `dartboard: "Blue Print Zero/Tasks"`). The `Task ID` from this existing DART task will be used in the Work Order.
*   **Action (Typically USER-directed, or by a designated planning persona like the Strategic Coherence Architect):**
    1.  Create a new Work Order document in the **"Blue Print Zero/Work Orders" folder in DART** using the `create_doc` MCP tool.
        *   **Document Title Convention:** `WO_<DART_TASKID>_<YYYYMMDD>_<3-5-word-label>` (e.g., `WO_ildO8Gz1EtoV_20250621_Vector-Database-Setup`). `<DART_TASKID>` is the ID from the **pre-existing Task** in **DART**, and `<YYYYMMDD>` is the WO creation date.
    2.  Populate the WO document with all mandatory contents (see Section 5).
    3.  Ensure the **DART task** for the related Task in "Blue Print Zero/Tasks" is updated to reflect the Work Order's existence and assignment if necessary (e.g., updating status or adding notes about the WO document title).

### 4.2. Work Order Assignment

*   The `Assigned Persona(s)` field in the WO document clearly designates who is responsible for execution (e.g., "Strategic Coherence Architect", "Code Mode").
*   The corresponding task in **"Blue Print Zero/Tasks" in DART** should also reflect this assignment.

### 4.3. Work Order Execution

*   The assigned persona (often an AI assistant guided by the user) takes the WO document as the primary directive.
*   The AI assistant should confirm its understanding of the WO's objectives and scope with the guiding user/persona.
*   Work is performed as detailed in the WO, utilizing specified input documents and aiming for the defined deliverables, adhering to Blueprint Zero principles.

### 4.4. Work Order Completion & Documentation Protocol (CRITICAL)

The completion of a Work Order is not just the creation of its primary deliverables but also the meticulous documentation of the work within the Blueprint Zero system. **All of the following steps are mandatory for a WO to be considered complete:**

1.  **Primary Deliverables Met:** All items listed under "Expected Deliverables/Outputs" in the WO have been produced and are in their correct locations (e.g., updated documents, code changes, analysis results).
2.  **Journal Entry Creation (DART Document Primary):**
    *   **Responsibility:** Executing Persona.
    *   **Action (Primary - DART Document):** Create a new **DART Document Journal Entry** using the `create_doc` MCP tool in the **"Blue Print Zero/Journal" folder**. This document serves as the primary, authoritative record of work progress and completion for this task.
        *   **Document Title:** Follow the `JE_<DART_TASKID>_<YYYYMMDD>_<summary>` pattern (e.g., `JE_ildO8Gz1EtoV_20250621_Vector-DB-Setup-Complete`).
        *   **Content:** Detailed work summary, debugging steps, learnings, decisions, and a list of all relevant files created, modified, or deleted. Must include explicit reference to the parent DART Task ID.
        *   **Linking:** The DART Document must be linked directly to its parent DART Task in "Blue Print Zero/Tasks", and the Task description should be updated with a markdown link to the DART Document (e.g., `[Document Title](document_htmlUrl)`).
        *   **Note:** For minor fixes or simple updates (like a tooling resolution that doesn't justify a full document), the DART Task description itself can serve as the journal entry, or a concise DART Document can be created.
    *   **Action (Optional - Local Journal File):** For very detailed, complex, or temporary notes that are not suitable for a concise DART Document, a local Markdown journal file *may* still be created in a designated local directory (e.g., `journal/`).
        *   **Filename:** `JE_<YYYYMMDD_HHMMSS>_<DART_TASKID>_<1-3-word-summary>.md` (e.g., `JE_20250621_143500_ildO8Gz1EtoV_DB-Notes.md`). `<YYYYMMDD_HHMMSS>` is the UTC timestamp, and `<DART_TASKID>` is from **DART**.
        *   **Content:** Should include explicit reference to the `Work Order` document title and the corresponding DART Task ID.
        *   **Important:** Local journal files are secondary and do **not** replace the mandatory DART Document Journal Entry.
3.  **Task Update in DART:**
    *   **Responsibility:** Executing Persona.
    *   **Action:** Update the status of the corresponding task (identified by `Related Task ID in DART:` in the WO document) in **"Blue Print Zero/Tasks" in DART** to `Done`.
        *   If a review stage is required by a different persona, the status may first be set to `Value Assessment` or `Review`.
        *   The task in **DART** should be updated to include notes about the `Work Order` document title and the title of the completion `Journal Entry`.
4.  **Hand-Off- Document Creation:**
    *   **Trigger:** A Hand-Off- Document is created if the completion of the current Work Order (WO1) has led to the USER-directed identification and creation of new, subsequent Work Order(s) (WO2, WO3, etc., each tied to a newly created Task in **"Blue Print Zero/Tasks" in DART**).
    *   **Purpose:** To provide essential context, outputs, and a "note to self" from the AI completing WO1 to the AI/session that will execute the subsequent WO(s).
    *   **Responsibility:** Executing Persona for WO1.
    *   **Action:**
        1.  Ensure the new follow-on Task(s) and corresponding Work Order(s) have been created as per USER direction (following protocol in 4.1).
        2.  Create a new Hand-Off- Document in the **"Blue Print Zero/Hand-Off- Documents" folder in DART** using the `create_doc` MCP tool.
            *   **Document Title:** Follow the `HO_<YYYYMMDD_HHMMSS>_<DART_TASKID_of_WO1>_<summary_of_WO1_completion>` pattern (e.g., `HO_20250621_144000_ildO8Gz1EtoV_DB-Setup-Handoff`). `<YYYYMMDD_HHMMSS>` is the UTC timestamp of HO creation.
        *   **Content:** Must include:
            *   Timestamp of HO creation.
            *   **Explicit reference to the completed `Work Order` document title (WO1).**
            *   **Explicit reference to the `Journal Entry` document title created for WO1's completion (as per step 4.4.2).**
            *   A concise summary of WO1's key outcomes, learnings, and the current project status relevant to the follow-on work.
            *   **Crucially, clear pointers to the newly created subsequent Work Order document title(s) (WO2, WO3, etc.) and their respective DART task ID(s).**
            *   Any specific advice, data, or context from WO1 that is vital for the successful execution of the subsequent WO(s).
5.  **Work Order Archival (Optional but Recommended):**
    *   While Dart manages documents, a process could be established to change the status or add a tag to completed Work Order documents in the "Blue Print Zero/Work Orders" folder to indicate completion, keeping the primary view focused on active WOs.

## 5. Work Order Document: Mandatory Contents

Each Work Order document (created in the "Blue Print Zero/Work Orders" folder in DART) **must** contain the following sections/information. This structure ensures all necessary context and requirements are captured.

1.  `Work Order Title:` (Clear, concise title following naming convention)
2.  `Work Order Status:` (e.g., `Open`, `In Progress`, `Blocked`, `Review`, `Done`)
3.  `Related Task ID in DART:` (The authoritative `id` of the corresponding task in **"Blue Print Zero/Tasks" in DART**. **MANDATORY LINKAGE.**)
4.  `Input Documents/Prerequisites:` (List of all relevant Blueprint Zero files, Dart documents, or external information needed to start, e.g., analysis reports, previous Hand-Off- docs, specific core documents like Q-level files or the Roadmap.)
5.  `Date Created:` (YYYY-MM-DD)
6.  `Created By Persona:` (The persona initiating the WO, e.g., "Strategic Coherence Architect")
7.  `Assigned Persona(s):` (The persona(s) responsible for execution, e.g., "Strategic Coherence Architect", "Code Mode")
8.  `Priority:` (e.g., `Critical`, `High`, `Medium`, `Low` - Optional, should align with DART task priority)
9.  `Due Date:` (YYYY-MM-DD - Optional, should align with DART task due date)
10. `Objective/Goal:` (A clear statement of what the WO aims to achieve within the Blueprint Zero context.)
11. `Background/Context:` (Brief explanation of why this WO is needed, referencing relevant Blueprint Zero documents or strategic goals.)
12. `Scope of Work / Detailed Tasks:` (A breakdown of the specific actions to be performed. Can be a checklist.)
13. `Expected Deliverables/Outputs:` (A clear list of what will be produced, e.g., new files in the repository, modified files, specific documentation updates in Dart, analysis results, with expected locations/Dart folders.)
14. `Completion Checklist (Cross-reference to Section 4.4):`
    *   [ ] Primary Deliverables Met
    *   [ ] Journal Entry Created (Document Title: ____________________)
    *   [ ] **DART Task Updated** (Task ID: _________ set to `Done`/`Value Assessment`/`Review`)
    *   [ ] Hand-Off- Document Created (Document Title: ____________________ - *Only if follow-on tasks/WOs created*)

## 6. Integration with Other Project Management Tools

### 6.1. DART (Task Management)

*   For every WO created, a corresponding task **must** be created in **"Blue Print Zero/Tasks" in DART**.
*   The **DART task** should include the `Work Order Title` in its description or notes for easy cross-referencing.
*   The status of the task in **DART** reflects the status of the WO.
*   **Task Creation:** Use DART MCP (`create_task`) to create tasks with proper tagging (e.g., "Architecture", "Workflow", "VectorDatabase") and priority.
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
*   **Task Queries:** Use DART MCP (`list_tasks`, `get_task`) to find tasks, filter by status, assignee, tags, or search by criteria.

### 6.2. DART Document Journal Entries (Primary Journaling)

*   **Primary Record:** All comprehensive journal entries detailing WO execution and completion are now managed as **DART Documents** created in the **"Blue Print Zero/Journal" folder**. This ensures centralized, searchable, and version-controlled documentation directly linked to DART Tasks.
*   **No `journal_index.yml`:** The `journal_index.yml` file is no longer required as DART natively manages the organization and discoverability of DART Documents.
*   **Local Journal Files (Optional):** Local Markdown files in a local `journal/` directory are now considered optional. They may be used for very detailed, temporary, or complex notes that are not suitable for direct inclusion in a concise DART Document. If used, they should still reference the `Work Order Title` and the corresponding **DART Task ID**.

### 6.3. Hand-Off- Documents

*   A Hand-Off- Document is **mandatory** upon WO completion if follow-up WOs are created, as per Section 4.4.4.
*   It is created as a document in the **"Blue Print Zero/Hand-Off- Documents" folder in DART**.
*   It summarizes the WO outcome and points to the detailed journal entry.
*   References both the completed WO (by title) and the newly created **DART tasks** (by ID) and their corresponding subsequent WO titles for subsequent work.

## 7. DART MCP Integration Benefits

The integration with DART MCP provides several advantages for the Blueprint Zero workflow:

*   **No File Parsing Issues:** AI assistants can query DART directly without truncation problems.
*   **Real-time Task Management:** Instant access to current task status and details.
*   **Rich Metadata:** Advanced filtering by status, assignee, tags, and custom properties.
*   **Cross-session Continuity:** Task and document context persists across different AI sessions and tools.
*   **Structured Queries:** Natural language task and document management via MCP tools.

## 8. Process Adherence

Strict adherence to this Blueprint Zero Work Order Process is crucial for maintaining project clarity, ensuring comprehensive documentation ("popcorn trail"), and facilitating seamless collaboration between all team members, especially when transitioning work between sessions or AI assistants. The integration with DART MCP enhances this process by providing robust, scalable task and document management within the designated "Blue Print Zero" space while preserving all established workflow principles.

## 9. Continuous Improvement: Pattern Identification and Documentation

As a core practice within Blueprint Zero, all participants in this workflow are **continuously engaged in identifying and documenting reusable patterns**—both "good patterns" (best practices, effective solutions) and "anti-patterns" (issues to avoid). This effort is crucial for building our collective knowledge base, accelerating future development, and preventing regressions.

When working on any task or Work Order, if you encounter a recurring problem, discover an elegant solution, or identify a new architectural standard relevant to Blueprint Zero, please consider documenting it as a dedicated "Pattern" document (e.g., in the `docs/` directory or a dedicated `docs/patterns/` subdirectory) and creating a corresponding DART task in "Blue Print Zero/Tasks" to track its integration into the vector database knowledge base. This proactive knowledge capture is a vital part of our commitment to AI-native software engineering within Blueprint Zero.

## 10. Strategic Coherence Architect's Role in Enforcement

The Strategic Coherence Architect persona is responsible for ensuring adherence to this Blueprint Zero workflow. This involves:

1.  **Modeling Correct Behavior:** Consistently following the defined workflow for its own tasks and documentation.
2.  **Monitoring and Identification:** Periodically reviewing the "Blue Print Zero" space in Dart to identify workflow deviations (e.g., missing links, incorrect naming, misplaced documents) using `list_tasks` and `list_docs`.
3.  **Flagging and Remediation:** Creating DART tasks or adding comments to flag non-compliant items for attention using `create_task` or `add_task_comment`.
4.  **Guidance and Clarification:** Assisting in clarifying workflow procedures and best practices, referencing this guide.
