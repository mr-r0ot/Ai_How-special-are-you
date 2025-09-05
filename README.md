# 🌟 Ai — *How Special Are You?*

> **Project:** Ai\_How-special-are-you
> **Author:** Mohammad Taha Gorji (@mr-r0ot)

---

[🔴 **Live Demo**](https://mr-r0ot.github.io/Ai_How-special-are-you) • [📁 GitHub Repository](https://github.com/mr-r0ot/Ai_How-special-are-you)

<p align="center">
  <img src="https://img.shields.io/badge/Author-Mohammad%20Taha%20Gorji-blue?style=for-the-badge" alt="author" />
  <img src="https://img.shields.io/badge/Tech-HTML%2FCSS%20%7C%20JavaScript-yellow?style=for-the-badge" alt="tech" />
  <img src="https://img.shields.io/badge/Model-Tree--based%20AI-green?style=for-the-badge" alt="model" />
  <img src="https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge" alt="license" />
</p>

---

## 🎯 Elevator Pitch

A privacy-first, browser-native experience that answers the whimsical—but meaningful—question: **How special am I among all humans?** The UI is crafted with modern HTML & CSS; the reasoning engine is a compact, tree-based AI implemented in vanilla JavaScript using validated statistical features.

---

## ✨ Highlights

* **Runs completely in the browser** — no server calls, preserving privacy.
* **Responsive, polished UI** built with semantic HTML and accessible CSS.
* **Tree-based decision engine** written in JavaScript — deterministic, auditable, and fast.
* **Uses validated statistical data** as input features (configurable JSON data files).
* **Easy to extend** — add new features, change weights, or swap in new decision rules.

---

## 🧭 How It Works — Architecture Overview

1. **Input layer (UI):** The user answers a short, friendly questionnaire (age, location bands, rare attributes, achievements, etc.). Inputs are normalized client-side.
2. **Feature mapping:** Inputs are converted to validated, privacy-preserving features (percentiles, rarity flags, sociodemographic buckets) using local lookup tables.
3. **Tree-based engine:** A deterministic decision tree analyzes features in a transparent sequence of rules and returns a scored result plus an interpretability trace explaining which branches were applied.
4. **Presentation:** The UI renders a visually appealing result panel that explains the score, rarity metrics, and suggestions for exploration.

This design favors interpretability and reproducibility over black-box “mystery.”

---

## 📊 Data & Validation

* The project ships with compact, preprocessed statistical lookup tables (JSON) representing global distributions for selected features.
* All data sources are documented in the `/data` folder (or `DATA-SOURCES.md`) and include provenance (source name, year, and the transformation steps used to generate percentiles).
* You can replace or update data files to reflect newer sources — the engine will adapt without code changes.

---

## 🔒 Privacy & Ethics

* **No data leaves the user’s browser.** All calculations and logs are local by default.
* The system intentionally avoids personally identifying prompts and stores nothing persistently unless the user opts in.
* The README includes an ethics appendix explaining assumptions, limitations, and recommended disclaimers for public deployments.

---

## 🚀 Quick Start — Run Locally

### Option A — Open in browser

1. Download or clone the repository.
2. Open `desktop.html` (or `index.html`) in your browser.

### Option B — Simple local HTTP server (recommended for modern browser features)

```bash
# Python 3
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

---

## 🛠️ Configuration & Customization

* **Feature definitions:** `/config/features.json` — define which user inputs map to which statistical fields.
* **Decision rules:** `/model/tree.json` — a human-readable, versioned tree description used by the JS engine.
* **UI text & copy:** `/i18n/en.json` — change labels, button text, and result phrasing.
* **Visual theme:** edit `/css/variables.css` to alter colors, fonts, and spacing.

Add new features by updating `features.json` and the tree rules; the engine includes a validation step that will show mismatches in the console.

---

## 📚 Example: Interpretable Result (sample)

```json
{
  "score": 87.2,
  "category": "Highly Uncommon",
  "explain": [
    "Top 2% worldwide percentile for creative achievements",
    "Belongs to a demographic bucket with <1% rarity for the combination of features"
  ],
  "trace": [
    {"node":"age_bucket","value":"25-34","effect":1.1},
    {"node":"achievement_score","value":95,"effect":2.3}
  ]
}
```

---

## 🧪 Testing & Quality

* Unit tests for the tree evaluator are included under `/tests` (vanilla JS with a small custom runner). Run them by opening `/tests/index.html` in a browser.
* The project includes sample test vectors in `/tests/vectors.json` to ensure determinism across browsers.

---

## ♿ Accessibility

* Semantic HTML and ARIA-friendly controls.
* Keyboard-first navigation for all interactive elements.
* High-contrast themes included in `/css/themes.css`.

---

## 🧩 Contribution Guide

1. Fork the repo and create a branch: `feature/your-feature`
2. Add tests if you modify the model or add data.
3. Open a Pull Request describing motivations and any data sources.

Please include source citations for any added statistical datasets.

---

## 🧾 License

This project is released under the **MIT License**. See `LICENSE` for details.

---

## 👤 Author

**Mohammad Taha Gorji** — contact: `mr-r0ot` on GitHub.
If you want to collaborate on data validation or alternative model ideas, open an issue.

---

## 📦 Appendix: Recommended Improvements

* Add a small visualization (radar or percentile bars) to make results more tangible.
* Offer a privacy-first export (download JSON) so users can store their own results offline.
* Add a server-side option for researchers who want aggregated, opt-in analytics with explicit consent.

---

> *Curious?* Try the live demo and open `developer tools → Console` to see the interpretability trace and the model’s deterministic decisions.
