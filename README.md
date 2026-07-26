# 🎮 DayZ Central Economy (CE) • absurdTypes

[![DayZ Version](https://img.shields.io/badge/DayZ-1.29%2B-red.svg)](https://dayz.com)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Format](https://img.shields.io/badge/Format-Single_File_HTML5-emerald.svg)]()
[![Privacy](https://img.shields.io/badge/Privacy-100%25_Client_Side-purple.svg)]()

> **Interactive Economy Diagnostics & Visual Dashboard for Server Owners, Administrators, and Developers.**  
> Effortlessly load 9,000+ Central Economy item definitions, identify fatal `min > nominal` infinite loop bugs, and rank top offending XML files causing server lag.

---

## 🌟 Key Features

* **⚡ Ultra-Fast Client-Side Parser:** Ingests large audit reports (`ABSURD_NOMINALS_FULL_REPORT_EN.md`) or raw DayZ economy XML files (`types.xml`, `custom_types/*.xml`) containing 9,000+ items instantly without freezing the browser.
* **📊 Executive KPI Dashboard:**
  * **Total Flagged Items Count**
  * **Fatal Loop Bugs (`min > nominal`):** Highlights items triggering infinite respawn loops.
  * **Requested World Item Load:** Calculates total requested nominals against the recommended 12,000 Chernarus healthy target.
  * **Server Capacity Overload Gauge:** Real-time visual capacity bar.
* **🔥 Ranked Offending XML Files / Mods Table:** Ranks all economy XML files by total item inflation and fatal loop counts, showing admins exactly which mod or config is killing server performance.
* **📖 Server Owner Explainer Guide:** In-app accordion guide explaining DayZ Central Economy terms (`nominal`, `min`, `quantmin`, `quantmax`) in simple, non-technical language.
* **🔍 Real-Time Search & Category Filters:**
  * Search instantly by item classname or XML file.
  * Filter pills: `All Items`, `🔴 Fatal min > nom`, `🔥 Extreme Nominal (>=100)`.
  * Column sorting (Nominal, Min, Lifetime, XML File).
* **📋 One-Click Developer Executive Summary:** Copies a clean, formatted Markdown summary to clipboard for easy handoff to server developers.

---

## 🛠️ How to Use

1. **Download / Open:** Open `absurdTypes.html` in any web browser (Chrome, Firefox, Edge, Safari). No installation or web server required.
2. **Load Data:** Drag and drop `ABSURD_NOMINALS_FULL_REPORT_EN.md` or any DayZ economy XML file (`types.xml`, `custom_types/vanilla_tools.xml`, etc.) into the drop zone.
3. **Analyze:**
   * Review the top KPI cards for server capacity overload.
   * Check the **Top Offending XML Files** table to identify worst-offending mod packs.
   * Click any XML file to filter the main table specifically to that file.
4. **Handoff:** Click **"Copy Dev Summary"** in the top header and send the summary to your server developer for execution.

---

## 📖 DayZ Central Economy (CE) Quick Reference

| XML Tag | Definition & Role | Golden Rule / Threshold |
| :--- | :--- | :--- |
| `<nominal>` | Target ceiling quantity of an item active in the world. (Acts as the max target count). | Chernarus server sum target: **8,000 – 12,000 items total**. |
| `<min>` | Floor threshold. When item count drops below `<min>`, respawn triggers until reaching `<nominal>`. | **CRITICAL:** `<min>` MUST be **less than or equal to** `<nominal>` (`min <= nominal`). |
| `<quantmin>` / `<quantmax>` | Item internal fill/ammo/capacity percentage (`0%` to `100%`). | `<quantmin>` MUST be **less than or equal to** `<quantmax>`. Value `-1` disables quantity. |
| `<restock>` | Delay in seconds before spawning the next item instance after dropping below `<min>`. | Standard: `0` to `900` seconds. |
| `<lifetime>` | Time in seconds an untouched item remains in the world before despawning. | Standard: `14400`s (4 hours) to `3888000`s (45 days for flags). |

---

## 🔒 Privacy & Performance

* **100% Client-Side:** All parsing and data processing happen entirely inside your web browser. No data or logs are ever uploaded to an external server.
* **Zero Dependencies Build:** Standalone HTML5 using TailwindCSS CDN and FontAwesome icons.

---

*Designed & Prepared by Eliana Noé — Server Health & Diagnostics Engine.*
