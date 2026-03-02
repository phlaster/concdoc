# concdoc

**concdoc** is a web-based PDF reader designed to help users maintain focus by tracking reading behavior and concentration metrics in real-time. It features a split-screen interface with a distraction-free reading environment on the left and live statistics on the right.

## Features

- **Drag-to-Scroll Navigation:** Mimics the physical sensation of moving a document. Pages are scrolled by dragging with the mouse.
- **Intelligent Auto-Pause:** Automatically detects when you stop reading. After 5 seconds of inactivity, the session pauses, ensuring statistics remain accurate.
- **Dual-Metric Tracking:**
    - **Focus Score:** A global, lifetime average of your reading time versus total elapsed time.
    - **Concentration:** A live, rolling average (default 2 minutes) calculated from differential measurements taken at configurable intervals.
- **Live Timeline:** Visualizes concentration over the last hour with smooth line charts.
- **Multi-Document Support:** Open multiple PDFs in tabs. All documents share a common statistics pool, tracking your overall study session.
- **Configurable Parameters:** Adjust the measurement interval, rolling average window, and history length via an in-app settings menu.
- **Local & Private:** Runs entirely in the browser. No data is sent to external servers.

## How to Use

1.  **Load a Document:** Click the "Upload" icon in the header or drag and drop a PDF file into the left panel.
2.  **Start Session:** Once loaded, click the "Ready to Focus" banner to start the timer.
3.  **Read:** Click and drag the document up or down to read.
4.  **Pause/Resume:** Release the mouse to read. If you stop moving the mouse for 5 seconds, the session will auto-pause (indicated by an overlay). Click the overlay to resume.
5.  **Monitor Stats:** Watch your Focus Score and live Concentration metrics update in the right panel.
6.  **Configure:** Use the gear icon near the timeline to adjust how concentration is calculated.

## Metrics Explained

**concdoc** distinguishes between two types of focus metrics to give you a better understanding of your reading habits:

1.  **Focus Score (Lifetime %):**
    - Located in the grid stats.
    - **Definition:** The ratio of *Active Reading Time* to *Total Elapsed Time* since the session began.
    - **Purpose:** Gives you a "big picture" view of your productivity for the entire session.

2.  **Concentration (Rolling Average %):**
    - Located in the circular progress indicator above the timeline.
    - **Definition:** The average concentration over a rolling window (default: last 2 minutes).
    - **Mechanism:** The system checks every second if you are actively reading (dragging) or paused. Every X seconds (default: 10s), it calculates a "differential score" (0-100%) for that specific slice of time. These scores are averaged to produce the live metric.
    - **Purpose:** Shows your current momentum. If this number drops, it means you've been idle or pausing frequently in the last few minutes.

## Configuration

The settings menu (gear icon) allows you to tune the sensitivity of the Concentration metric:

- **Measurement Interval (sec):** How often the system calculates a new differential score (Default: 10s).
- **Rolling Average Window (min):** The timeframe used to calculate the live "Concentration" percentage (Default: 2 min).
- **History Length (min):** How far back the Timeline chart displays data (Default: 60 min).

## Tech Stack

- **Frontend:** HTML5, CSS3 (Tailwind CSS via CDN), Vanilla JavaScript (ES6+).
- **PDF Rendering:** [PDF.js](https://mozilla.github.io/pdf.js/) - Mozilla's PDF rendering library.
- **Data Visualization:** [Chart.js](https://www.chartjs.org/) - For the live concentration timeline.

> This project is made with assistance of GLM-5 by [Z.ai](https://chat.z.ai)