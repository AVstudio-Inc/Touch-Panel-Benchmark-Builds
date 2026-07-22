# TouchPanelMark™ v1.0.0 — Deployment & Usage Guide

> **Commercial Touch Panel Benchmark & Diagnostic Suite**  
> *Created by [AVstudio Inc](https://avstudio.app)*

---

## 📦 Build Archive Contents

This directory contains pre-compiled, production-ready release archives for **TouchPanelMark™ v1.0.0**:

| File / Archive | Target Platform | Description |
| :--- | :--- | :--- |
| **`TouchPanelMark_v1.0.0.ch5z`** | Crestron CH5 Touch Panels | Compiled Crestron CH5 deployment archive |
| **`TouchPanelMark_v1.0.0.zip`** | AVstudio AVS-10 / Commercial Web | Standalone HTML5 web release ZIP archive |

---

## 📲 How to Load & Deploy to Touch Panels

### Method 1: Deploying to Crestron Touch Panels (TSW-1070, TSW-1080, TSW-770, etc.)

#### Option A: Direct Web Interface (Recommended Browser Method)
1. Open a browser and navigate to your Crestron touch panel IP address:
   ```
   http://<TOUCH_PANEL_IP>
   ```
2. Log in with panel administrator credentials.
3. Select **Upload Project** from the menu on the left side.
4. Select `TouchPanelMark_v1.0.0.ch5z` and click **Upload**.

#### Option B: Via Crestron CH5 Utilities CLI (Command Line)
```bash
npx @crestron/ch5-utilities-cli deploy -i <TOUCH_PANEL_IP> -p TouchPanelMark_v1.0.0.ch5z
```

#### Option C: Via Crestron Toolbox
1. Open **Crestron Toolbox** → **Web XPanel / CH5 Project Upload**.
2. Connect to the panel's IP address, select `TouchPanelMark_v1.0.0.ch5z`, and click **Upload**.

---

### Method 2: Deploying to AVstudio AVS-10 Touch Panels

#### Direct Web Management Portal (Recommended Browser Method)
1. Open a browser and navigate to the AVS-10 management portal:
   ```
   http://<AVS10_IP>/manage
   ```
2. Authenticate with panel administrator credentials.
3. Select **Upload Project** from the management menu.
4. Select `TouchPanelMark_v1.0.0.zip` (or `.ch5z` project archive) and click **Upload**.

---

## 🧪 How to Execute & Benchmark Touch Panels

### Step 1: Verify / Select Panel Model
Upon loading, TouchPanelMark automatically detects device hardware signatures. You can verify or override the active model using the **`[ Select Panel Model ▾ ]`** dropdown in the top header bar.

### Step 2: Run Automated Benchmark Suite
1. Tap the blue **`▶ Run All Tests`** button in the top right header bar (or tap `Run Automated Benchmark Suite` on the home view).
2. The software executes 6 core web engine tests sequentially:
   - **DOM Scale & Reflow Engine**: Measures un-virtualized DOM node limits (up to 20,000 elements) before frame drops.
   - **Graphics & Hardware Acceleration**: Evaluates 2D Canvas particles and CSS transform animation FPS.
   - **JavaScript & SoC Compute Engine**: Stresses main-thread array operations, math loops, and heavy JSON parse/serialization.
   - **Touch Input & Latency Sampling**: Tap/touch the interactive target area when prompted to sample millisecond response latency and 10-point multi-touch capability.
   - **Control IPC Throughput**: Simulates rapid join update bursts (up to 2,000 updates/sec).
   - **Memory & GC Pause Detector**: Measures main-thread Garbage Collection freezes.

### Step 3: Inspect & Export Audit Reports
Upon suite completion, TouchPanelMark opens the **Final Report** view:
- **Performance Rating Tier**: Inspect overall score (`0–1000 pts`), efficiency (`XX.X%`), and rating tier (`S-Tier`, `A-Tier`, `B-Tier`, `C-Tier`, `D/F-Tier`).
- **Download PDF**: Tap **`Download PDF`** in the toolbar to save a clean PDF audit document locally (`TouchPanelMark_Report_<Model>_<Timestamp>.pdf`).
- **Gofile Cloud Upload & QR Code**: Tap **`Upload to Gofile.io`** to publish the report to the cloud and display a large **QR Code** on screen for mobile phone scanning.
- **Panel Matrix Comparison**: Tap **Panel Matrix** in the top navigation bar to compare your panel's score side-by-side against **AVstudio AVS-10** and **Crestron TSW-1080**.

---

## 🏢 Support & Contact

**TouchPanelMark™** is designed and maintained by **AVstudio Inc**.

- **Website**: [https://avstudio.app](https://avstudio.app)
- **Copyright**: © 2026 AVstudio Inc. All rights reserved.
