# mutu

Evaluate an app's quality with an ISO 9126 scorecard — 21 questions, a score out of 105,
and a printable PDF report.

## How it works

Enter the name of the app you want to evaluate, then rate each sub-characteristic from
1 (Sangat Kurang) to 5 (Sangat Baik) across the 6 ISO 9126 characteristics:

| Characteristic | Sub-characteristics |
|---|---|
| Functionality | Suitability, Accuracy, Interoperability, Security |
| Reliability | Maturity, Availability, Fault tolerance |
| Usability | Learnability, Operability, User error protection, Accessibility |
| Efficiency | Time behavior, Resource utilization |
| Maintainability | Modularity, Reusability, Analysability, Modifiability |
| Portability | Adaptability, Installability, Replaceability |

Your progress is saved in the browser (localStorage), so an unfinished evaluation can be
resumed later. At the end you get a total score out of 105, a quality percentage, and a
category:

| Score | Category |
|---|---|
| ≤ 41 | ❌ Broken (Aplikasi Rusak / Tidak Layak) |
| ≤ 62 | ⚠️ Kurang Optimal (Banyak Kekurangan) |
| ≤ 77 | ⚠️ Biasa Saja (Layak digunakan, Tapi Kurang Memuaskan) |
| ≤ 92 | 👍 Bagus (Sebagian Besar Sudah Baik) |
| > 92 | ✅ Super Bagus (Sangat Layak dan Direkomendasikan) |

The result can be exported as a PDF report (jsPDF) with the full question-by-question breakdown.

## Usage

No build step needed — it's a static page:

1. Open `index.html` in a browser (or serve the folder, e.g. `python -m http.server`).
2. Enter the app name, answer the 21 questions, and view the result.
3. Click **Cetak PDF** to download the evaluation report.

## Tech

- Vanilla JavaScript, HTML, CSS
- jsPDF + jsPDF-AutoTable (PDF export, via CDN)
- localStorage for progress saving
