# Bits-Codeforge-Dixitha

# BITS Pilani Digital — Advanced Grading Console

A client-side web application designed for academic instructors to review examination datasets, analyze student score distributions, configure dynamic grade cut-offs, and export finalized grade rosters.

---

## 🌟 Live Deployment

- **Live Application:** [https://dixthasys.github.io/Bits-Codeforge-Dixitha/](https://dixthasys.github.io/Bits-Codeforge-Dixitha/)
- **Hosting Platform:** GitHub Pages (Enforced HTTPS)
- **Entry Point:** `index.html`

---

## ⚙️ System Capabilities & Workflow

1. **Workbook Ingestion & Schema Parsing:**
   - Ingests `.xlsx`, `.xls`, and `.csv` files entirely in-browser using binary array buffers.
   - Automatically standardizes column attributes across identifier, course, and mark fields.
   - Extracts unique courses into dynamic selectors.

2. **Cohort Analytics & Visualizations:**
   - Real-time descriptive statistical modeling: Minimum, Maximum, Arithmetic Mean, and Median.
   - Dynamic 10-bin score frequency histogram rendered via HTML5 Canvas.
   - Cohort distribution curve calculation with variance-sensitive rendering.

3. **Grade Boundary Configuration:**
   - Real-time configuration for standard grading bands: `A`, `A-`, `B`, `B-`, `C`, `C-`, `D`, and `E`.
   - Continuous range cascading ensuring adjacent boundaries are synchronized.
   - Instant live feedback indicating student headcounts per grade tier.

4. **Continuous Boundary Validation:**
   - Real-time mathematical verification requiring `Min < Max` for all bands.
   - Detection of gaps and overlaps across contiguous grade intervals.
   - State-locked export controls preventing download of invalid configurations.

5. **Grade Export Pipeline:**
   - Generates RFC 4180-compliant CSV rosters with proper string quoting.
   - Preserves complete cohort data with explicit assignment tracking.
   - Session timer tracking active review duration.

---

## 📥 Data Schema & Format Specifications

The application processes structured examination data with the following schema:

| Field | Type | Constraints | Description |
|---|---|---|---|
| **Student's BITS ID** | String | Alphanumeric (e.g. `2024XXXX`) | Unique institutional student identifier |
| **Course** | String | Non-empty text | Assigned course or module title |
| **Total Marks** | Integer | 0 – 100 scale | Examination score rounded to nearest whole integer |

---

## 💻 Technical Architecture & Stack

- **Runtime Environment:** Pure client-side browser execution (zero server dependency)
- **Markup & Layout:** Semantic HTML5, CSS Grid, Flexbox
- **Logic & State Engine:** Vanilla JavaScript (ES6+ modular closures)
- **Spreadsheet Processing:** [SheetJS (xlsx)](https://cdn.jsdelivr.net/npm/xlsx/dist/xlsx.full.min.js) via `FileReader` `ArrayBuffer`
- **Graphics Pipeline:** HTML5 Canvas 2D Context API (`requestAnimationFrame` animation loops)
- **Infrastructure:** GitHub Pages Static Web Hosting with automated SSL/TLS

---

## 🛠️ Local Development & Execution

1. Clone repository:
   ```bash
   git clone https://github.com/dixthasys/Bits-Codeforge-Dixitha.git
   cd Bits-Codeforge-Dixitha
   ```

2. Open the application:
   - Directly open `index.html` in any modern web browser (Chrome, Edge, Firefox, Safari), or
   - Serve using a local HTTP server:
     ```bash
     npx serve .
     ```

3. Load examination marks using the included dataset:
   - File: `Student-marks.xlsx`

---

## 👤 Author

- **Author:** Dixitha R
- **Repository:** [dixthasys/Bits-Codeforge-Dixitha](https://github.com/dixthasys/Bits-Codeforge-Dixitha)
