<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>New GitHub Repository — Ultra Modern</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* ===== Root Variables ===== */
  :root {
    --bg: #0b0c10;
    --panel: rgba(255, 255, 255, 0.04);
    --border: rgba(255, 255, 255, 0.08);
    --text: #e8e9ef;
    --accent: #5ac8ff;
    --accent-glow: 0 0 16px rgba(90, 200, 255, 0.6);
    --radius: 18px;
  }

  /* ===== Base Styles ===== */
  body {
    margin: 0;
    background: var(--bg);
    color: var(--text);
    font-family: "Inter", sans-serif;
    line-height: 1.7;
    -webkit-font-smoothing: antialiased;
  }

  /* ===== Header ===== */
  header {
    text-align: center;
    padding: 90px 20px 60px;
  }

  header h1 {
    margin: 0;
    font-size: 48px;
    letter-spacing: -1px;
    background: linear-gradient(90deg, #5ac8ff, #8df3ff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 6px rgba(90,200,255,0.4));
  }

  header p {
    margin-top: 18px;
    opacity: 0.75;
    font-size: 18px;
  }

  /* ===== Container ===== */
  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px 70px;
  }

  /* ===== Section Blocks ===== */
  .block {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 32px;
    margin-bottom: 32px;
    backdrop-filter: blur(12px);
    transition: 0.25s ease;
  }

  .block:hover {
    border-color: var(--accent);
    box-shadow: var(--accent-glow);
    transform: translateY(-4px);
  }

  h2 {
    margin-top: 0;
    font-size: 24px;
    border-bottom: 1px solid var(--border);
    padding-bottom: 12px;
    letter-spacing: 0.3px;
  }

  /* ===== Code Snippets ===== */
  pre {
    background: rgba(255,255,255,0.06);
    padding: 18px;
    border-radius: var(--radius);
    border: 1px solid var(--border);
    overflow-x: auto;
  }

  code {
    color: var(--accent);
    font-size: 15px;
  }

  /* ===== Links ===== */
  a {
    color: var(--accent);
    text-decoration: none;
    transition: 0.2s;
  }

  a:hover {
    text-shadow: var(--accent-glow);
  }

  /* ===== Footer ===== */
  footer {
    text-align: center;
    opacity: 0.55;
    padding: 40px 0 50px;
    font-size: 15px;
  }
</style>
</head>

<body>

<header>
  <h1>my-new-repository</h1>
  <p>A next-gen starter template for GitHub projects — clean, modern, elegant</p>
</header>

<div class="container">

  <div class="block">
    <h2>📌 Project Overview</h2>
    <p>
      This repository serves as a foundation for modern development projects.  
      It includes a clean structure, ready-to-use documentation layout, and optimized formatting.
    </p>
  </div>

  <div class="block">
    <h2>🚀 Getting Started</h2>
    <p>Clone the repository:</p>
    <pre><code>git clone https://github.com/USERNAME/my-new-repository.git
cd my-new-repository</code></pre>
  </div>

  <div class="block">
    <h2>📁 Project Structure</h2>
    <pre><code>/
├── index.html
├── src/
│   └── app.js
└── docs/
    └── documentation.md</code></pre>
  </div>

  <div class="block">
    <h2>🔗 Useful Links</h2>
    <p>GitHub Repository:  
      <a href="#">https://github.com/USERNAME/my-new-repository</a>
    </p>
    <p>Live Preview (GitHub Pages):  
      <code>https://USERNAME.github.io/my-new-repository/</code>
    </p>
  </div>

</div>

<footer>
  Built with ❤️ — Customize <code>index.html</code> to make it yours.
</footer>

</body>
</html>
