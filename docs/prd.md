Great — here’s a **project-agnostic, full PRD with user stories and acceptance criteria** for your **Status Report Generator**. This is written so you can drop it directly into `docs/PRD.md` and also hand it to v0 (Vercel) to scaffold components.

---

# Status Report Generator (Designer v1) – Product Requirements Document

## Overview

The **Status Report Generator** is a lightweight web tool for creating polished, executive-ready status reports. It allows users to input structured content (program/project summary, statuses, executive summary, lowlights, and updates), customize design elements, and export the report as clean HTML.

The tool runs entirely in the browser with local persistence and requires no backend.

---

## Goals

* Provide a **structured workflow** for creating standardized status reports.
* Support **real-time preview** of reports while editing.
* Allow for **design customization** (fonts, colors, density, borders, custom CSS).
* Make exporting **fast and simple** (copy, download).
* Ensure **data safety** via sanitization and local-only storage.

---

## Non-Goals

* Multi-user collaboration (future stretch).
* Backend storage or authentication (first release is client-side only).
* Advanced WYSIWYG editing beyond basic bold/italic/underline.

---

## Target Users

* **Project / Program Managers (PM/TPM):** Generate weekly or sprint status reports.
* **Executives & Sponsors:** Consume standardized, easy-to-read reports.
* **Engineering Teams:** Use reports to align stakeholders on progress and risks.

---

## Core Features

### 1. Content Input

* **Program/Project Summary:** Free-form text area.
* **Status Indicators:** Dropdowns for last status, current status, trending, and a date selector.
* **Ownership Fields:** Inputs for Report Owner, Engineering DRI, Business Sponsor, Technical Sponsor.
* **Executive Summary:** Rich text area with bold, italic, underline controls.
* **Lowlights:** Free-form textarea, interpreted as one per line.
* **Updates:** Track name, team members, and a rich text update panel.

### 2. Design Customization

* Font selector (Inter, Arial, Segoe UI, Helvetica, Georgia).
* Accent color picker.
* Density options (comfortable vs compact).
* Table border style (lines vs shaded).
* Custom CSS injection.

### 3. Output and Preview

* Real-time preview rendered in the browser.
* Export panel showing raw generated HTML.
* Buttons for Generate, Copy HTML, Download HTML, Reset Saved Fields.

### 4. Persistence

* Uses `localStorage` to save summary, ownership fields, updates, and design settings.
* Reset button clears saved values.

### 5. Security

* Input sanitization to strip unsafe tags and attributes.
* Allows only safe formatting tags (`b`, `i`, `u`, `p`, `ul`, `li`, `table`, `a`).

---

## User Stories & Acceptance Criteria

### Story 1: Program/Project Summary

**As a report owner,** I want to enter a short description of the program/project so that readers understand the scope.

* [ ] Summary field accepts multi-line input.
* [ ] Summary renders as paragraphs in the preview/output.

---

### Story 2: Status Indicators

**As a report owner,** I want to set last status, current status, trending, and date so that stakeholders see the project health.

* [ ] Status dropdowns provide three values (Green, Yellow, Red).
* [ ] Statuses render as colored pills (green, yellow, red).
* [ ] Date renders in localized short format (e.g., Jan 5, 2025).

---

### Story 3: Ownership Fields

**As a report owner,** I want to assign accountability fields (owner, DRI, sponsors) so that stakeholders know who is responsible.

* [ ] Four ownership fields exist: Report Owner, Engineering DRI, Business Sponsor, Technical Sponsor.
* [ ] Values display in a summary table with consistent formatting.

---

### Story 4: Executive Summary

**As a report owner,** I want to provide a high-level summary with formatting so that I can emphasize key points.

* [ ] Rich text controls apply `<b>`, `<i>`, `<u>` formatting.
* [ ] Output sanitization preserves only safe formatting.
* [ ] Content renders in preview immediately after editing.

---

### Story 5: Lowlights

**As a report owner,** I want to list challenges as bullet points so that stakeholders can quickly scan them.

* [ ] Multi-line text input is converted into `<ul><li>` list.
* [ ] Blank lines are ignored.

---

### Story 6: Updates

**As a report owner,** I want to capture track/team updates so that detailed progress is recorded.

* [ ] Track name and team members fields available.
* [ ] Updates panel accepts pasted rich or plain text.
* [ ] Toolbar options include “Paste Plain Text” and “Clear Updates.”
* [ ] Output sanitization ensures safe HTML.

---

### Story 7: Design Customization

**As a report owner,** I want to choose fonts, colors, and table styles so that reports match desired aesthetics.

* [ ] Font selector applies chosen font to preview/output.
* [ ] Accent color field updates theme variables.
* [ ] Density selector changes table padding.
* [ ] Border style toggles between lines and shaded rows.
* [ ] Custom CSS textarea appends styles to output.

---

### Story 8: Preview and Export

**As a report owner,** I want to preview and export reports so that I can share them externally.

* [ ] Live preview updates automatically on input change.
* [ ] “Generate” builds HTML and renders to preview/output.
* [ ] “Copy HTML” copies code to clipboard.
* [ ] “Download HTML” saves as `status-report.html`.

---

### Story 9: Persistence

**As a user,** I want my inputs saved in the browser so that I don’t lose work when reloading.

* [ ] Fields auto-persist to localStorage.
* [ ] Reset button clears saved values.

---

### Story 10: Security

**As a user,** I want confidence that the tool won’t inject malicious content so that exported reports are safe.

* [ ] Sanitizer removes disallowed tags and attributes.
* [ ] `javascript:` URLs are stripped from links.

---

## Stretch Goals

* Export to **PDF** and **Markdown**.
* Support **cloud sync** for collaboration.
* Provide **template variants** (weekly, sprint, quarterly).
* Add authentication and profiles to sync settings across devices.

---

## Assumptions

* Runs entirely in browser (no backend).
* Uses modern browser APIs (Clipboard, File, localStorage).
* Optimized for **short reports** (weekly/monthly), not long documents.

---


