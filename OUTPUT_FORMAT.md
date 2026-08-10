# Experiment PDF Output Format & Guidelines

This document outlines the mandatory layout, structure, and styling standards for all experiment PDF reports in this repository (`pravinraj213/low-code-zoho-creator`).

---

## 1. Document Title & Header Format

* **Starting Title**: Each PDF must start directly at the top of Page 1 with the experiment title formatted as:
  `Exp <Num>: <Title>`
  * *Example*: `Exp 1: Comparative Study of Low-Code vs. Traditional Development`
  * *Example*: `Exp 2: Zoho Creator Account Setup and Architecture`
* **Excluded Elements**:
  * **No Subject Code**: Do NOT include subject codes (such as `CB23F35`) in the title or page headers.
  * **No Student Info Block**: Do NOT include student name, register number, or branch blocks in the header text block.
  * **No Top Running Banners**: Do NOT include repetitive running top headers across pages.

---

## 2. Perfectly Centered Page Overlay Watermark

* **Watermark Text**: Every page of the generated PDF report must feature the roll number watermark:
  `241401070`
* **Watermark Overlay Placement**:
  * Positioned using a full-page flexbox container (`width: 100%; height: 100%; display: flex; align-items: center; justify-content: center; z-index: 99999`) on top of all text, tables, and images.
  * Rotated at `-38deg` in translucent dark gray (`rgba(50, 50, 50, 0.18)`), mathematically centered across the exact geometric midpoint of every A4 page box.

---

## 3. Internal Document Structure

For each single-experiment report:
1. **No Table of Contents**: Exclude Table of Contents sections.
2. **No Objective Section**: Exclude dedicated "Objective" headers/sections.
3. **Core Sections**:
   - **Introduction / Scope**: Contextual background and goals.
   - **Procedure / Technical Sections**: Detailed step-by-step procedure, CLI commands, scripting snippets, and platform component breakdown.
   - **Output / Screenshots**: High-resolution screenshots embedded with centered italicized captions (e.g., *Figure 1: Microservices screen in Zoho Creator*).
   - **Observations**: Bulleted summary of key findings.
   - **Conclusion**: Final summary statement confirming successful completion.

---

## 4. Image & PDF Compilation Standard

* All images must be preserved in high quality (PNG/JPEG) and scaled cleanly within container widths (`max-width: 95%`).
* PDFs can be generated via HTML/CSS compiled with headless Chromium:
  ```bash
  chromium-browser --headless --disable-gpu --no-pdf-header-footer --print-to-pdf=<OutputFile.pdf> <InputHtml.html>
  ```
