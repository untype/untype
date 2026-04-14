<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Peter Henry — GitHub Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Instrument+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  /* ── TOKYO NIGHT PALETTE ──────────────────────
     bg:        #1a1b26
     bg-alt:    #16161e
     surface:   #24283b
     surface2:  #2a2f45
     border:    #3b4261
     muted:     #565f89
     fg:        #c0caf5
     fg-dim:    #9aa5ce
     blue:      #7aa2f7
     cyan:      #7dcfff
     teal:      #2ac3de
     green:     #9ece6a
     purple:    #bb9af7
     pink:      #f7768e
     orange:    #ff9e64
  ─────────────────────────────────────────────── */
  :root {
    --bg:       #1a1b26;
    --bg-alt:   #16161e;
    --surface:  #24283b;
    --surface2: #2a2f45;
    --border:   #3b4261;
    --muted:    #565f89;
    --fg:       #c0caf5;
    --fg-dim:   #9aa5ce;
    --blue:     #7aa2f7;
    --cyan:     #7dcfff;
    --teal:     #2ac3de;
    --green:    #9ece6a;
    --purple:   #bb9af7;
    --pink:     #f7768e;
    --orange:   #ff9e64;
    --rule:     rgba(59,66,97,0.7);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--fg);
    font-family: 'Instrument Sans', sans-serif;
    font-size: 15px;
    line-height: 1.65;
    max-width: 880px;
    margin: 0 auto;
    padding: 3rem 2rem 5rem;
  }

  .header {
    border-bottom: 1px solid var(--border);
    padding-bottom: 2.25rem;
    margin-bottom: 3rem;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 2rem;
    align-items: end;
  }

  .header-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    color: var(--pink);
    margin-bottom: 0.6rem;
  }

  .header-name {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2.6rem, 5.5vw, 3.8rem);
    line-height: 1.0;
    letter-spacing: -0.02em;
    margin-bottom: 0.8rem;
    background: linear-gradient(90deg, var(--blue) 0%, var(--purple) 55%, var(--pink) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .header-title {
    font-size: 14.5px;
    color: var(--fg-dim);
    font-weight: 400;
    max-width: 460px;
    line-height: 1.65;
  }

  .header-meta {
    display: flex;
    flex-direction: column;
    gap: 0.45rem;
    align-items: flex-end;
  }

  .meta-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.06em;
    color: var(--fg-dim);
    background: var(--surface);
    border: 0.5px solid var(--border);
    padding: 4px 11px;
    border-radius: 3px;
    white-space: nowrap;
  }

  .meta-tag.blue   { border-color: rgba(122,162,247,0.5); color: var(--blue); }
  .meta-tag.purple { border-color: rgba(187,154,247,0.5); color: var(--purple); }
  .meta-tag.teal   { border-color: rgba(42,195,222,0.5);  color: var(--teal); }
  .meta-tag.green  { border-color: rgba(158,206,106,0.5); color: var(--green); }

  .section { margin-bottom: 3rem; }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 1.25rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 0.5px;
    background: var(--rule);
  }

  .about-text {
    font-size: 15.5px;
    line-height: 1.82;
    color: var(--fg-dim);
    max-width: 720px;
  }

  .about-text strong { font-weight: 600; color: var(--blue); }
  .about-text em     { font-style: normal; color: var(--purple); font-weight: 500; }

  /* Timeline */
  .timeline { display: flex; flex-direction: column; }

  .timeline-item {
    display: grid;
    grid-template-columns: 110px 1fr;
    gap: 1rem;
    padding: 1rem 0 1rem 1.5rem;
    border-left: 1px solid var(--border);
    position: relative;
  }

  .timeline-item::before {
    content: '';
    position: absolute;
    left: -4.5px;
    top: 1.35rem;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--surface2);
    border: 1.5px solid var(--border);
  }

  .timeline-item.active::before {
    background: var(--blue);
    border-color: var(--blue);
    box-shadow: 0 0 10px rgba(122,162,247,0.4);
  }

  .timeline-era {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.08em;
    color: var(--muted);
    padding-top: 3px;
    line-height: 1.4;
    text-transform: uppercase;
  }

  .timeline-role {
    font-size: 14px;
    font-weight: 600;
    color: var(--fg);
    margin-bottom: 4px;
  }

  .timeline-desc {
    font-size: 13px;
    color: var(--fg-dim);
    line-height: 1.6;
  }

  /* Focus cards — 3-col grid */
  .focus-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 10px;
  }

  .focus-card {
    background: var(--surface);
    border: 0.5px solid var(--border);
    border-radius: 7px;
    padding: 1.1rem 1.25rem 1.25rem;
  }

  .focus-card-tag {
    font-family: 'DM Mono', monospace;
    font-size: 9.5px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
    display: block;
  }

  .focus-card-tag.blue   { color: var(--blue); }
  .focus-card-tag.teal   { color: var(--teal); }
  .focus-card-tag.purple { color: var(--purple); }
  .focus-card-tag.green  { color: var(--green); }
  .focus-card-tag.orange { color: var(--orange); }
  .focus-card-tag.pink   { color: var(--pink); }

  .focus-card h3 {
    font-size: 13.5px;
    font-weight: 600;
    color: var(--fg);
    margin-bottom: 0.45rem;
    line-height: 1.3;
  }

  .focus-card p {
    font-size: 12.5px;
    color: var(--fg-dim);
    line-height: 1.6;
  }

  /* Stack grid */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
    gap: 10px;
  }

  .stack-group {
    background: var(--surface);
    border: 0.5px solid var(--border);
    border-radius: 7px;
    overflow: hidden;
  }

  .stack-group-header {
    font-family: 'DM Mono', monospace;
    font-size: 9.5px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 7px 12px;
    background: var(--surface2);
    color: var(--muted);
    font-weight: 500;
    border-bottom: 0.5px solid var(--border);
  }

  .stack-group-header.blue   { color: var(--blue); }
  .stack-group-header.teal   { color: var(--teal); }
  .stack-group-header.purple { color: var(--purple); }
  .stack-group-header.green  { color: var(--green); }
  .stack-group-header.orange { color: var(--orange); }

  .stack-items {
    padding: 8px 12px 10px;
    display: flex;
    flex-direction: column;
    gap: 5px;
  }

  .stack-item {
    font-size: 12.5px;
    color: var(--fg-dim);
    line-height: 1.5;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .stack-item .dot {
    width: 4px;
    height: 4px;
    border-radius: 50%;
    background: var(--muted);
    flex-shrink: 0;
  }

  /* Emerging */
  .emerging-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
    gap: 10px;
  }

  .emerging-item {
    border-left: 2px solid var(--border);
    padding: 10px 14px;
    background: var(--surface);
    border-radius: 0 6px 6px 0;
  }

  .emerging-item.blue   { border-left-color: var(--blue); }
  .emerging-item.teal   { border-left-color: var(--teal); }
  .emerging-item.purple { border-left-color: var(--purple); }
  .emerging-item.green  { border-left-color: var(--green); }
  .emerging-item.orange { border-left-color: var(--orange); }

  .emerging-item h4 {
    font-size: 13px;
    font-weight: 600;
    color: var(--fg);
    margin-bottom: 3px;
  }

  .emerging-item p {
    font-size: 12px;
    color: var(--fg-dim);
    line-height: 1.55;
  }

  /* Pills */
  .pill-row { display: flex; flex-wrap: wrap; gap: 7px; }

  .pill {
    font-size: 12.5px;
    color: var(--fg-dim);
    background: var(--surface);
    border: 0.5px solid var(--border);
    padding: 5px 13px;
    border-radius: 100px;
  }

  /* Connect */
  .connect-strip { display: flex; gap: 1.25rem; flex-wrap: wrap; margin-top: 0.25rem; }

  .connect-link {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.05em;
    color: var(--blue);
    text-decoration: none;
    border-bottom: 0.5px solid rgba(122,162,247,0.4);
    padding-bottom: 1px;
  }

  /* Footer */
  .footer {
    margin-top: 4rem;
    padding-top: 1.5rem;
    border-top: 0.5px solid var(--border);
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    color: var(--muted);
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  hr.divider {
    border: none;
    border-top: 0.5px solid var(--rule);
    margin: 2.5rem 0;
  }

  @media (max-width: 680px) {
    .header        { grid-template-columns: 1fr; }
    .header-meta   { align-items: flex-start; flex-direction: row; flex-wrap: wrap; }
    .focus-grid    { grid-template-columns: 1fr 1fr; }
    .stack-grid    { grid-template-columns: 1fr 1fr; }
    .timeline-item { grid-template-columns: 70px 1fr; }
  }

  @media (max-width: 440px) {
    .focus-grid { grid-template-columns: 1fr; }
    .stack-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header class="header">
  <div>
    <p class="header-eyebrow">GitHub Profile</p>
    <h1 class="header-name">Peter Henry</h1>
    <p class="header-title">Senior AI Analyst · Former Senior Intelligence Analyst · Building agents, automations, and data systems that do genuinely useful things</p>
  </div>
  <div class="header-meta">
    <span class="meta-tag blue">Python · SQL</span>
    <span class="meta-tag purple">AI &amp; Agents</span>
    <span class="meta-tag teal">Data Engineering</span>
    <span class="meta-tag green">Power BI</span>
  </div>
</header>

<!-- ABOUT -->
<section class="section">
  <p class="section-label">About</p>
  <p class="about-text">
    I came up as a <strong>Senior Intelligence Analyst</strong> — trained to find signal in noise, structure ambiguous problems, and turn complex information into clear decisions under pressure. That same operating mode now drives my work in AI. As a <strong>Senior AI Analyst</strong> I design, evaluate, and build agentic systems, automation pipelines, and data infrastructure. I also <em>pilot emerging technologies</em> before they're mainstream — running real assessments, POC builds, and adoption frameworks that move organisations from curiosity to capability. In my own time I prototype and experiment, building agents for the sheer interest of it.
  </p>
</section>

<hr class="divider">

<!-- BACKGROUND -->
<section class="section">
  <p class="section-label">Background</p>
  <div class="timeline">

    <div class="timeline-item active">
      <div class="timeline-era">Now</div>
      <div>
        <p class="timeline-role">Senior AI Analyst</p>
        <p class="timeline-desc">Agentic systems design and evaluation, AI tool piloting, automation workflows, and data engineering in Databricks. Bridging intelligence tradecraft with emerging AI capabilities.</p>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-era">Previously</div>
      <div>
        <p class="timeline-role">Senior Intelligence Analyst</p>
        <p class="timeline-desc">Structured analysis under ambiguity, intelligence production, data discovery, and communicating findings to decision-makers. SQL, Python, and Power BI as primary tools.</p>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-era">Throughout</div>
      <div>
        <p class="timeline-role">Data Visualisation &amp; Automation</p>
        <p class="timeline-desc">Power BI dashboards and reporting pipelines. Automation of manual workflows via scripting, Power Automate, and n8n. A consistent thread: make data legible and make repetitive work disappear.</p>
      </div>
    </div>

  </div>
</section>

<hr class="divider">

<!-- WHAT I WORK ON -->
<section class="section">
  <p class="section-label">What I work on</p>
  <div class="focus-grid">

    <div class="focus-card">
      <span class="focus-card-tag purple">Agentic Systems</span>
      <h3>Multi-Agent Design &amp; Evaluation</h3>
      <p>Orchestration, memory, tool use, and human-in-the-loop patterns. POC through to production-readiness assessment.</p>
    </div>

    <div class="focus-card">
      <span class="focus-card-tag pink">Technology Piloting</span>
      <h3>Emerging AI Adoption</h3>
      <p>Structured pilots and POC evaluations of new AI tools — building the evidence base for real adoption decisions.</p>
    </div>

    <div class="focus-card">
      <span class="focus-card-tag blue">Web Intelligence</span>
      <h3>AI-Driven Data Collection</h3>
      <p>Agent-driven web scraping, structured extraction, and monitoring frameworks. Scaling intelligence gathering with AI.</p>
    </div>

    <div class="focus-card">
      <span class="focus-card-tag teal">Automation</span>
      <h3>Workflow Integration</h3>
      <p>Connecting AI to enterprise systems via n8n, Power Automate, and MCP-based tool pipelines that people actually use.</p>
    </div>

    <div class="focus-card">
      <span class="focus-card-tag green">Data Engineering</span>
      <h3>Lakehouse &amp; Analytics</h3>
      <p>Databricks, PySpark, dbt. Raw data into clean, queryable assets that feed intelligent systems and clear dashboards.</p>
    </div>

    <div class="focus-card">
      <span class="focus-card-tag orange">Visualisation</span>
      <h3>Power BI &amp; Reporting</h3>
      <p>End-to-end reporting pipelines and dashboards. Making data legible for people who need to act on it, not just look at it.</p>
    </div>

  </div>
</section>

<hr class="divider">

<!-- TECH STACK -->
<section class="section">
  <p class="section-label">Tech stack</p>
  <div class="stack-grid">

    <div class="stack-group">
      <div class="stack-group-header purple">Agent &amp; Orchestration</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>LangFlow</span>
        <span class="stack-item"><span class="dot"></span>CrewAI</span>
        <span class="stack-item"><span class="dot"></span>Dify</span>
        <span class="stack-item"><span class="dot"></span>MCP (Model Context Protocol)</span>
        <span class="stack-item"><span class="dot"></span>Pidev · Hermes</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-header teal">Automation &amp; Workflow</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>n8n</span>
        <span class="stack-item"><span class="dot"></span>Power Automate</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-header blue">Web AI &amp; Scraping</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>AgentQL</span>
        <span class="stack-item"><span class="dot"></span>Firecrawl (SDK + API + MCP)</span>
        <span class="stack-item"><span class="dot"></span>Playwright (async)</span>
        <span class="stack-item"><span class="dot"></span>BeautifulSoup · lxml</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-header green">Data &amp; AI Engineering</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>Databricks (Lakehouse, PySpark)</span>
        <span class="stack-item"><span class="dot"></span>dbt</span>
        <span class="stack-item"><span class="dot"></span>DuckDB</span>
        <span class="stack-item"><span class="dot"></span>SQL Server</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-header orange">Visualisation</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>Power BI</span>
        <span class="stack-item"><span class="dot"></span>Matplotlib · Plotly</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-header blue">Languages &amp; Core</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>Python (FastAPI, Pandas, Polars)</span>
        <span class="stack-item"><span class="dot"></span>SQL</span>
        <span class="stack-item"><span class="dot"></span>Astral UV</span>
        <span class="stack-item"><span class="dot"></span>REST APIs</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-header">GenAI Platforms</div>
      <div class="stack-items">
        <span class="stack-item"><span class="dot"></span>Legora</span>
        <span class="stack-item"><span class="dot"></span>Harvey AI (pilot)</span>
        <span class="stack-item"><span class="dot"></span>Claude · GPT · Gemini</span>
      </div>
    </div>

  </div>
</section>

<hr class="divider">

<!-- CURRENTLY EXPLORING -->
<section class="section">
  <p class="section-label">Currently watching &amp; exploring</p>
  <div class="emerging-grid">

    <div class="emerging-item blue">
      <h4>LangGraph</h4>
      <p>Stateful, graph-based multi-agent orchestration — the standard for complex branching workflows in 2026</p>
    </div>

    <div class="emerging-item teal">
      <h4>A2A Protocol</h4>
      <p>Google's agent-to-agent communication standard — cross-platform interoperability for agent fleets</p>
    </div>

    <div class="emerging-item purple">
      <h4>Browser Use</h4>
      <p>Agent-native browser automation — 78k GitHub stars, rapidly replacing Playwright for agentic web tasks</p>
    </div>

    <div class="emerging-item blue">
      <h4>Mem0 / Agent Memory</h4>
      <p>Persistent memory layers — episodic, semantic, and procedural memory that makes agents genuinely useful over time</p>
    </div>

    <div class="emerging-item teal">
      <h4>Crawl4AI</h4>
      <p>LLM-optimised web crawling — clean markdown output purpose-built for feeding language models</p>
    </div>

    <div class="emerging-item purple">
      <h4>Composio</h4>
      <p>Open-source tool integration layer — auth-managed connectors for plugging agents into real enterprise apps</p>
    </div>

    <div class="emerging-item green">
      <h4>AutoGen v0.4</h4>
      <p>Microsoft's redesigned multi-agent framework — async, event-driven, built for production</p>
    </div>

    <div class="emerging-item orange">
      <h4>Agent Observability</h4>
      <p>LangSmith, LangFuse, Arize — tracing, evaluation and monitoring for agents running at scale</p>
    </div>

  </div>
</section>

<hr class="divider">

<!-- INTERESTS -->
<section class="section">
  <p class="section-label">Interests &amp; background</p>
  <div class="pill-row">
    <span class="pill">Intelligence analysis</span>
    <span class="pill">Multi-agent systems</span>
    <span class="pill">Data visualisation</span>
    <span class="pill">Technology piloting</span>
    <span class="pill">Web intelligence</span>
    <span class="pill">Workflow automation</span>
    <span class="pill">AI for professional services</span>
    <span class="pill">Prompt engineering</span>
    <span class="pill">Data discovery</span>
    <span class="pill">Open source</span>
    <span class="pill">Ergonomic keyboards</span>
    <span class="pill">Colemak DH</span>
  </div>
</section>

<hr class="divider">

<!-- CONNECT -->
<section class="section">
  <p class="section-label">Connect</p>
  <div class="connect-strip">
    <a class="connect-link" href="https://github.com/untype">github.com/untype</a>
  </div>
</section>

<!-- FOOTER -->
<footer class="footer">
  <span>Peter Henry</span>
  <span>Senior Intelligence Analyst → Senior AI Analyst</span>
</footer>

</body>
</html>
