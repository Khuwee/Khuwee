<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Khuwe RedReaper — GitHub Profile</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --green:      #39ff14;
      --green-dim:  #1a7a0a;
      --bg:         #0d1117;
      --surface:    #161b22;
      --surface2:   #21262d;
      --border:     #30363d;
      --text:       #e6edf3;
      --muted:      #8b949e;
      --red:        #ff5555;
      --amber:      #f0883e;
      --blue:       #58a6ff;
      --purple:     #bc8cff;
    }

    html, body {
      background: var(--bg);
      color: var(--text);
      font-family: 'JetBrains Mono', monospace;
      font-size: 14px;
      line-height: 1.65;
      min-height: 100vh;
    }

    body {
      display: flex;
      justify-content: center;
      padding: 40px 16px 60px;
    }

    .readme {
      width: 100%;
      max-width: 860px;
    }

    /* ── Terminal window ─────────────────────────────── */
    .terminal {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
      margin-bottom: 20px;
      box-shadow: 0 8px 32px rgba(0,0,0,0.5);
    }

    .terminal-bar {
      background: var(--surface2);
      padding: 11px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
      border-bottom: 1px solid var(--border);
    }

    .dot { width: 12px; height: 12px; border-radius: 50%; flex-shrink: 0; }
    .dot-r { background: #ff5f57; }
    .dot-y { background: #febc2e; }
    .dot-g { background: #28c840; }

    .bar-title {
      flex: 1;
      text-align: center;
      font-size: 11px;
      color: var(--muted);
      letter-spacing: 0.04em;
    }

    .terminal-body { padding: 24px 28px 28px; }

    /* ── ASCII header ────────────────────────────────── */
    .ascii {
      font-size: 10px;
      line-height: 1.25;
      color: var(--green);
      margin-bottom: 22px;
      white-space: pre;
      overflow-x: auto;
      text-shadow: 0 0 8px rgba(57,255,20,0.35);
    }

    /* ── Prompt line ─────────────────────────────────── */
    .prompt-line {
      display: flex;
      align-items: baseline;
      flex-wrap: wrap;
      gap: 5px;
      margin-bottom: 6px;
      font-size: 13px;
    }

    .pu { color: var(--blue); }
    .ph { color: var(--purple); }
    .pp { color: var(--amber); }
    .pm { color: var(--muted); }
    .pc { color: var(--text); }

    /* ── Output block ────────────────────────────────── */
    .output {
      margin: 6px 0 20px;
      padding: 14px 18px;
      background: rgba(0,0,0,0.28);
      border-left: 2px solid var(--green-dim);
      border-radius: 0 6px 6px 0;
    }

    .out-row {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      margin-bottom: 8px;
      font-size: 13px;
    }
    .out-row:last-child { margin-bottom: 0; }

    .out-icon { min-width: 18px; font-size: 15px; }
    .out-val  { color: var(--text); }
    .out-val a { color: var(--blue); text-decoration: none; }
    .out-val a:hover { text-decoration: underline; }

    .g  { color: var(--green);  }
    .a  { color: var(--amber);  }
    .b  { color: var(--blue);   }
    .p  { color: var(--purple); }
    .r  { color: var(--red);    }

    /* ── Divider ─────────────────────────────────────── */
    hr {
      border: none;
      border-top: 1px solid var(--border);
      margin: 20px 0;
    }

    /* ── Skills grid ─────────────────────────────────── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(185px, 1fr));
      gap: 12px;
      margin: 10px 0;
    }

    .skill-block {
      background: rgba(0,0,0,0.22);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 12px 14px;
    }

    .skill-cat {
      font-size: 10px;
      letter-spacing: 0.09em;
      text-transform: uppercase;
      margin-bottom: 9px;
    }

    .tags { display: flex; flex-wrap: wrap; gap: 5px; }

    .tag {
      font-size: 10px;
      padding: 2px 7px;
      border-radius: 4px;
      background: var(--surface);
      border: 1px solid var(--border);
      color: var(--muted);
    }

    .tag-g { color: var(--green);  border-color: var(--green-dim); }
    .tag-b { color: var(--blue);   border-color: #1f6feb; }
    .tag-a { color: var(--amber);  border-color: #7d4e1a; }
    .tag-p { color: var(--purple); border-color: #553098; }

    /* ── Social links ────────────────────────────────── */
    .socials {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 10px;
    }

    .social {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      padding: 6px 14px;
      border: 1px solid var(--border);
      border-radius: 6px;
      text-decoration: none;
      font-size: 12px;
      color: var(--muted);
      transition: border-color 0.18s, color 0.18s;
    }
    .social:hover { border-color: var(--green); color: var(--green); }
    .social i { font-size: 16px; }

    /* ── Cursor blink ────────────────────────────────── */
    .cursor {
      display: inline-block;
      width: 9px; height: 15px;
      background: var(--green);
      vertical-align: middle;
      margin-left: 4px;
      animation: blink 1s step-end infinite;
    }
    @keyframes blink { 50% { opacity: 0; } }

    /* ── Responsive ──────────────────────────────────── */
    @media (max-width: 600px) {
      .terminal-body { padding: 16px 16px 20px; }
      .ascii { font-size: 7.5px; }
      .skills-grid { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>
<main class="readme">
  <div class="terminal">

    <!-- title bar -->
    <div class="terminal-bar">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="bar-title">khuwe@redreaper:~$ whoami</span>
    </div>

    <div class="terminal-body">

      <!-- ASCII header -->
      <div class="ascii"> _  __ _                               ____            _ ____
| |/ /| |__  _   _ __      __ ___   |  _ \ ___  __| |  _ \ ___  __ _ _ __   ___ _ __
| ' / | '_ \| | | |\ \ /\ / // _ \  | |_) / _ \/ _` | |_) / _ \/ _` | '_ \ / _ \ '__|
| . \ | | | | |_| | \ V  V /|  __/  |  _ <  __/ (_| |  _ <  __/ (_| | |_) |  __/ |
|_|\_\|_| |_|\__,_|  \_/\_/  \___|  |_| \_\___|\__,_|_| \_\___|\__,_| .__/ \___|_|
                                                                       |_|
  Offensive Security · MSSP Architecture · Fortinet · Southern Africa</div>

      <!-- Profile -->
      <div class="prompt-line">
        <span class="pu">khuwe</span><span class="pm">@</span><span class="ph">redreaper</span><span class="pm">:</span><span class="pp">~/profile</span><span class="pm">$</span>
        <span class="pc">cat identity.json</span>
      </div>
      <div class="output">
        <div class="out-row"><span class="out-icon">🔒</span><span class="out-val"><span class="g">Onalethata Lesley Khuwe</span> — Cybersecurity Engineer &amp; Offensive Security Practitioner</span></div>
        <div class="out-row"><span class="out-icon">📍</span><span class="out-val">Gaborone, Botswana &nbsp;·&nbsp; <span class="a">ROI / Blue Pearl Communications Pty Ltd</span></span></div>
        <div class="out-row"><span class="out-icon">🎓</span><span class="out-val">BSc (Hons) Network Systems Engineering — University of Sunderland</span></div>
        <div class="out-row"><span class="out-icon">🏅</span><span class="out-val"><span class="b">NSE7 Certified</span> &nbsp;|&nbsp; Pursuing <span class="p">CRTA</span> (Certified Red Team Analyst)</span></div>
        <div class="out-row"><span class="out-icon">⚡</span><span class="out-val">Reduced SOC client onboarding time by <span class="g">50%+</span> through end-to-end workflow automation</span></div>
      </div>

      <hr />

      <!-- Current status -->
      <div class="prompt-line">
        <span class="pu">khuwe</span><span class="pm">@</span><span class="ph">redreaper</span><span class="pm">:</span><span class="pp">~/status</span><span class="pm">$</span>
        <span class="pc">tail -n 4 current.log</span>
      </div>
      <div class="output">
        <div class="out-row"><span class="out-icon">🔭</span><span class="out-val"><span class="a">Working on:</span> MSSP Security Lab — Proxmox · FortiGate 60F · Wazuh SIEM · Windows Server 2022 AD · Kali Linux — client-facing demo platform for managed security services</span></div>
        <div class="out-row"><span class="out-icon">🌱</span><span class="out-val"><span class="a">Learning:</span> Red team tradecraft via <span class="p">CRTA</span> — attack-path validation, pentest methodology &amp; adversarial simulation</span></div>
        <div class="out-row"><span class="out-icon">🤝</span><span class="out-val"><span class="a">Open to:</span> MSSP architecture, Fortinet / Check Point solution design, offensive security lab collabs</span></div>
        <div class="out-row"><span class="out-icon">💬</span><span class="out-val"><span class="a">Ask me about:</span> SOC ops · NodeZero autonomous assessments · Fortinet/Check Point architecture · technical pre-sales</span></div>
      </div>

      <hr />

      <!-- Arsenal -->
      <div class="prompt-line">
        <span class="pu">khuwe</span><span class="pm">@</span><span class="ph">redreaper</span><span class="pm">:</span><span class="pp">~/arsenal</span><span class="pm">$</span>
        <span class="pc">ls --category --all</span>
      </div>

      <div class="skills-grid">
        <div class="skill-block">
          <div class="skill-cat g">// Offensive</div>
          <div class="tags">
            <span class="tag tag-g">Kali Linux</span>
            <span class="tag tag-g">Metasploit</span>
            <span class="tag tag-g">NodeZero</span>
            <span class="tag tag-g">Nmap</span>
            <span class="tag tag-g">Nikto</span>
            <span class="tag tag-g">CRTA (WIP)</span>
            <span class="tag tag-g">Greenbone CE</span>
          </div>
        </div>

        <div class="skill-block">
          <div class="skill-cat b">// SIEM &amp; Defensive</div>
          <div class="tags">
            <span class="tag tag-b">Wazuh</span>
            <span class="tag tag-b">FortiSIEM</span>
            <span class="tag tag-b">FortiAnalyzer</span>
            <span class="tag tag-b">DefectDojo</span>
            <span class="tag tag-b">Lynis</span>
            <span class="tag tag-b">SOC Operations</span>
          </div>
        </div>

        <div class="skill-block">
          <div class="skill-cat a">// Infrastructure</div>
          <div class="tags">
            <span class="tag tag-a">Proxmox</span>
            <span class="tag tag-a">FortiGate</span>
            <span class="tag tag-a">Check Point</span>
            <span class="tag tag-a">Tailscale VPN</span>
            <span class="tag tag-a">Windows AD</span>
            <span class="tag tag-a">HP ProCurve</span>
          </div>
        </div>

        <div class="skill-block">
          <div class="skill-cat p">// GRC &amp; MSSP</div>
          <div class="tags">
            <span class="tag tag-p">ISO 27001</span>
            <span class="tag tag-p">MSSP Design</span>
            <span class="tag tag-p">Securden PAM</span>
            <span class="tag tag-p">Risk Management</span>
            <span class="tag tag-p">Tender Prep</span>
            <span class="tag tag-p">Pre-Sales</span>
          </div>
        </div>
      </div>

      <hr />

      <!-- Fun fact -->
      <div class="prompt-line">
        <span class="pu">khuwe</span><span class="pm">@</span><span class="ph">redreaper</span><span class="pm">:</span><span class="pp">~/misc</span><span class="pm">$</span>
        <span class="pc">cat fun_fact.txt</span>
      </div>
      <div class="output">
        <div class="out-row">
          <span class="out-icon">🎯</span>
          <span class="out-val">I cut SOC client onboarding time by <span class="g">50%+</span> just by automating the parts everyone hated doing manually — because manual processes are just unwritten vulnerabilities.</span>
        </div>
      </div>

      <hr />

      <!-- Socials -->
      <div class="prompt-line">
        <span class="pu">khuwe</span><span class="pm">@</span><span class="ph">redreaper</span><span class="pm">:</span><span class="pp">~/connect</span><span class="pm">$</span>
        <span class="pc">./reach_out.sh</span>
      </div>

      <div class="socials">
        <a class="social" href="https://www.linkedin.com/in/onalethata-lesley-khuwe-203614223" target="_blank" rel="noopener">
          <i class="ti ti-brand-linkedin"></i> LinkedIn
        </a>
        <a class="social" href="https://khuwe-redreaper.github.io" target="_blank" rel="noopener">
          <i class="ti ti-world"></i> Portfolio
        </a>
        <a class="social" href="https://github.com/Khuwe-RedReaper" target="_blank" rel="noopener">
          <i class="ti ti-brand-github"></i> GitHub
        </a>
        <a class="social" href="mailto:YOUR_EMAIL_HERE">
          <i class="ti ti-mail"></i> Email
        </a>
      </div>

      <!-- Cursor -->
      <div style="margin-top: 24px; font-size: 13px; color: var(--muted);">
        <span class="g">❯</span>&nbsp;<span class="cursor"></span>
      </div>

    </div><!-- /terminal-body -->
  </div><!-- /terminal -->
</main>
</body>
</html>
