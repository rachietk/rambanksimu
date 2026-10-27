# RAM Bank Interleaving Simulator (COA Mini Project)

A responsive browser-based simulator made with HTML, CSS, and vanilla JavaScript. No framework, build step, or package installation is required.

## Features
- 2, 4, or 8 configurable memory banks
- Configurable memory size, access latency, and bank recovery time
- Low-order and high-order address mapping
- Sequential and interleaved scheduling comparison
- Bank timeline, request log, performance metrics, and throughput chart
- Interactive address-to-bank checker
- Responsive layout for desktop and mobile

## Run locally in VS Code on Ubuntu

1. Extract the ZIP.
2. Open the extracted folder in VS Code: **File → Open Folder**.
3. Open `index.html`.
4. Easiest option: install the **Live Server** extension by Ritwick Dey from the VS Code Extensions panel.
5. Right-click `index.html` and choose **Open with Live Server**.

No Node.js or compiler is needed. You can also open `index.html` directly in Firefox or Chrome, although Live Server is convenient during development.

## Host it free with GitHub Pages

1. Sign in to GitHub and create a new public repository, for example `ram-bank-interleaving-simulator`.
2. Upload `index.html`, `style.css`, `script.js`, and `README.md` to the repository root.
3. Open the repository's **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then click **Save**.
6. Wait for deployment. GitHub will show the published site URL in the Pages section.

Alternative hosting: Netlify can deploy the folder by drag-and-drop. This is a static website, so it does not need a backend or server.

## Model notes / assumptions

- Low-order mapping: `bank = address % numberOfBanks`; `localAddress = floor(address / numberOfBanks)`.
- High-order mapping divides the address space into contiguous blocks, one block per bank.
- The simulator models a simplified scheduler. Sequential mode waits for each access to finish. Interleaved mode allows requests to different ready banks to overlap, while each bank remains unavailable until access latency plus recovery time has elapsed.
- The chart is an illustrative throughput comparison across bank counts. Metrics are educational estimates, not a benchmark of physical RAM.
- Requests wrap around at the configured memory size if the start address plus request count exceeds it.

## Viva topics to prepare
1. What is memory interleaving?
2. Difference between low-order and high-order interleaving?
3. What is a bank conflict?
4. Does interleaving reduce the latency of one memory access?
5. How do latency and recovery time affect throughput?
6. Why may adding more banks fail to provide linear speedup?
