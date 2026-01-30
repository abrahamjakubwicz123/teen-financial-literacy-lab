<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="Teen Financial Literacy Lab — free, practical money workshops for students." />
  <title>Teen Financial Literacy Lab</title>

  <style>
    :root{
      --bg:#070b18;
      --panel:#0e1633;
      --panel2:#0b122a;
      --text:#eef1ff;
      --muted:#b9c2ffcc;
      --border:#27305a;
      --accent:#7c5cff;
      --accent2:#2fe6c4;
      --warn:#ff5c7c;
      --radius:18px;
      --shadow: 0 12px 34px rgba(0,0,0,.35);
      --max: 1100px;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
    }

    *{ box-sizing:border-box; }
    body{
      margin:0;
      font-family:var(--sans);
      color:var(--text);
      background:
        radial-gradient(900px 500px at 15% 10%, rgba(124,92,255,.22), transparent 62%),
        radial-gradient(900px 500px at 80% 20%, rgba(47,230,196,.16), transparent 58%),
        radial-gradient(900px 600px at 45% 95%, rgba(124,92,255,.16), transparent 60%),
        var(--bg);
      line-height:1.35;
    }

    a{ color:inherit; text-decoration:none; }
    .wrap{ max-width:var(--max); margin:0 auto; padding:0 18px; }

    /* Nav */
    .nav{
      position:sticky; top:0; z-index:20;
      backdrop-filter: blur(10px);
      background: rgba(7,11,24,.55);
      border-bottom:1px solid rgba(39,48,90,.8);
    }
    .nav-inner{
      display:flex; align-items:center; justify-content:space-between;
      padding:14px 0; gap:12px;
    }
    .brand{ display:flex; align-items:center; gap:10px; font-weight:900; }
    .logo{
      width:38px; height:38px; border-radius:14px;
      background: linear-gradient(135deg, var(--accent2), var(--accent));
      box-shadow: var(--shadow);
      position:relative;
    }
    .logo:after{
      content:"TFL";
      position:absolute; inset:0;
      display:grid; place-items:center;
      color:#0a0f22;
      font-size:13px;
      font-weight:1000;
      letter-spacing:.6px;
    }
    .menu{ display:flex; gap:10px; flex-wrap:wrap; align-items:center; justify-content:flex-end; }
    .pill{
      padding:10px 12px;
      border-radius:999px;
      border:1px solid rgba(39,48,90,.95);
      background: rgba(14,22,51,.55);
      color: var(--muted);
      font-weight:750;
      transition:.2s ease;
    }
    .pill:hover{ transform: translateY(-1px); border-color: rgba(124,92,255,.9); color: var(--text); }
    .cta{
      padding:10px 14px;
      border-radius:999px;
      border:0;
      font-weight:950;
      cursor:pointer;
      color:#061022;
      background: linear-gradient(135deg, var(--accent2), var(--accent));
      box-shadow: var(--shadow);
      transition:.2s ease;
    }
    .cta:hover{ transform: translateY(-1px); filter: brightness(1.04); }

    /* Hero */
    header.hero{ padding:52px 0 24px; }
    .hero-grid{
      display:grid;
      grid-template-columns: 1.2fr .8fr;
      gap:14px;
      align-items:stretch;
    }
    @media (max-width: 920px){
      .hero-grid{ grid-template-columns: 1fr; }
    }
    .card{
      border:1px solid rgba(39,48,90,.85);
      border-radius: var(--radius);
      background: linear-gradient(180deg, rgba(14,22,51,.72), rgba(11,18,42,.72));
      box-shadow: var(--shadow);
    }
    .hero-main{ padding:26px; position:relative; overflow:hidden; }
    .hero-main:before{
      content:"";
      position:absolute;
      width:520px; height:520px;
      top:-220px; left:-220px;
      background: radial-gradient(circle at 30% 30%, rgba(47,230,196,.18), transparent 60%);
      pointer-events:none;
    }
    .badge{
      display:inline-flex; align-items:center; gap:8px;
      padding:7px 10px;
      border-radius:999px;
      border:1px solid rgba(39,48,90,.95);
      background: rgba(7,11,24,.18);
      color: var(--muted);
      font-weight:800;
      width: fit-content;
    }
    .dot{
      width:10px; height:10px; border-radius:99px;
      background: var(--accent2);
      box-shadow: 0 0 0 6px rgba(47,230,196,.14);
    }
    h1{
      margin:10px 0 10px;
      font-size: clamp(30px, 4vw, 48px);
      line-height:1.05;
      letter-spacing:-.6px;
    }
    .sub{
      margin:0 0 16px;
      color: var(--muted);
      font-size: 16.5px;
      max-width: 60ch;
      font-weight:650;
    }
    .hero-actions{ display:flex; gap:10px; flex-wrap:wrap; align-items:center; margin-top: 14px; }
    .ghost{
      padding:10px 14px;
      border-radius:999px;
      border:1px solid rgba(39,48,90,.95);
      background: rgba(7,11,24,.12);
      color: var(--text);
      font-weight:900;
      cursor:pointer;
    }
    .ghost:hover{ border-color: rgba(47,230,196,.9); transform: translateY(-1px); }
    .warn{
      margin-top:16px;
      padding:10px 12px;
      border-radius: 12px;
      border:1px solid rgba(255,92,124,.35);
      background: rgba(255,92,124,.08);
      color: #ffd6de;
      font-weight:750;
      font-size: 12.5px;
    }

    .side{ padding:20px; display:flex; flex-direction:column; gap:12px; }
    .kpis{ display:grid; grid-template-columns: 1fr 1fr; gap:10px; }
    .kpi{
      border:1px solid rgba(39,48,90,.85);
      border-radius: 14px;
      background: rgba(7,11,24,.18);
      padding:12px;
    }
    .kpi b{ display:block; font-size:18px; }
    .kpi span{ color: var(--muted); font-weight:750; font-size:12.5px; }

    /* Sections */
    section{ padding:22px 0; }
    .section-title{
      display:flex; align-items:flex-end; justify-content:space-between;
      gap:10px; margin: 8px 0 12px;
    }
    .section-title h2{ margin:0; font-size:22px; letter-spacing:-.2px; }
    .section-title p{ margin:0; color:var(--muted); font-weight:650; font-size:13.5px; max-width:65ch; }

    .grid3{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:12px;
    }
    @media (max-width: 920px){ .grid3{ grid-template-columns: 1fr; } }

    .tile{
      padding:18px;
      border-radius: var(--radius);
      border:1px solid rgba(39,48,90,.85);
      background: rgba(14,22,51,.55);
      box-shadow: var(--shadow);
    }
    .tile h3{ margin:0 0 8px; font-size:16.5px; }
    .tile p{ margin:0 0 12px; color: var(--muted); font-weight:650; }
    .link{
      display:inline-flex; gap:8px; align-items:center;
      font-weight:950;
      padding:10px 12px;
      border-radius: 12px;
      border:1px solid rgba(39,48,90,.95);
      background: rgba(7,11,24,.16);
      transition:.2s ease;
    }
    .link:hover{ border-color: rgba(124,92,255,.9); transform: translateY(-1px); }

    /* Two column panels */
    .cols{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:12px;
      align-items:start;
    }
    @media (max-width: 920px){ .cols{ grid-template-columns: 1fr; } }

    .panel{
      padding:18px;
      border-radius: var(--radius);
      border:1px solid rgba(39,48,90,.85);
      background: rgba(11,18,42,.75);
      box-shadow: var(--shadow);
    }
    .panel h3{ margin:0 0 10px; }
    .label{
      font-size: 12px;
      color: var(--muted);
      font-weight: 850;
      margin: 8px 0 6px;
    }
    input, select, textarea{
      width:100%;
      padding:10px 12px;
      border-radius: 12px;
      border:1px solid rgba(39,48,90,.95);
      background: rgba(7,11,24,.35);
      color: var(--text);
      outline:none;
      font-weight:650;
    }
    textarea{ min-height: 120px; resize: vertical; }
    .row{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:10px;
    }
    @media (max-width: 560px){ .row{ grid-template-columns: 1fr; } }

    .btn{
      width:100%;
      padding:11px 14px;
      border-radius: 12px;
      border:0;
      cursor:pointer;
      font-weight:1000;
      color:#061022;
      background: linear-gradient(135deg, var(--accent2), var(--accent));
      box-shadow: var(--shadow);
      transition:.2s ease;
    }
    .btn:hover{ transform: translateY(-1px); filter: brightness(1.03); }

    .result{
      margin-top:12px;
      padding:12px;
      border-radius: 14px;
      border:1px solid rgba(39,48,90,.85);
      background: rgba(7,11,24,.18);
      font-family: var(--mono);
      font-size: 13px;
      white-space: pre-wrap;
    }

    /* Footer */
    footer{
      padding:28px 0 44px;
      color: var(--muted);
      font-weight:650;
      border-top:1px solid rgba(39,48,90,.6);
      margin-top: 18px;
    }
    .foot{ display:flex; justify-content:space-between; gap:14px; flex-wrap:wrap; align-items:flex-start; }
    .small{ font-size:12.5px; max-width: 75ch; }
    .mono{ font-family: var(--mono); font-size:12.5px; }
    .hide{ display:none; }
  </style>
</head>

<body>
  <div class="nav">
    <div class="wrap nav-inner">
      <div class="brand">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <div style="line-height:1; font-size:14px; opacity:.95;">Teen Financial Literacy Lab</div>
          <div style="font-size:12px; color:var(--muted); font-weight:800;">Free workshops • Practical money skills</div>
        </div>
      </div>

      <div class="menu">
        <a class="pill" href="#workshops">Workshops</a>
        <a class="pill" href="#partners">Partner</a>
        <a class="pill" href="#resources">Resources</a>
        <a class="pill" href="#about">About</a>
        <button class="cta" onclick="scrollToId('partners')">Request a Workshop</button>
      </div>
    </div>
  </div>

  <header class="hero">
    <div class="wrap hero-grid">
      <div class="card hero-main">
        <div class="badge"><span class="dot"></span> Student-led • Educational only</div>
        <h1>Free, real-life money skills for teens.</h1>
        <p class="sub">
          Teen Financial Literacy Lab delivers hands-on workshops on budgeting, saving, credit, and investing basics—built for
          middle & high school students.
        </p>

        <div class="hero-actions">
          <button class="cta" onclick="scrollToId('workshops')">See Workshops</button>
          <button class="ghost" onclick="scrollToId('partners')">Bring Us to Your School</button>
          <a class="pill" href="#resources">Get free tools</a>
        </div>

        <div class="warn">
          We don’t provide personalized financial or investing advice. Everything here is educational.
        </div>
      </div>

      <div class="card side">
        <div class="badge"><span class="dot"></span> Impact tracking</div>
        <div class="kpis">
          <div class="kpi"><b id="kpiWorkshops">0</b><span>workshops delivered</span></div>
          <div class="kpi"><b id="kpiStudents">0</b><span>students taught</span></div>
          <div class="kpi"><b id="kpiPartners">0</b><span>schools/partners</span></div>
          <div class="kpi"><b id="kpiVols">0</b><span>student volunteers</span></div>
        </div>

        <div class="tile" style="box-shadow:none;">
          <h3>Start a chapter</h3>
          <p>Want a club at your school? We’ll share a starter kit and curriculum.</p>
          <a class="link" href="#partners">Request the Chapter Kit →</a>
        </div>
      </div>
    </div>
  </header>

  <main class="wrap">
    <section id="workshops">
      <div class="section-title">
        <div>
          <h2>Workshop modules</h2>
          <p>Each session is 45–60 minutes: mini-lesson + activity + Q&A. Pick one module or combine two for a longer program.</p>
        </div>
      </div>

      <div class="grid3">
        <div class="tile">
          <h3>1) Budgeting Basics</h3>
          <p>Income vs expenses, needs vs wants, and a simple monthly budget you can actually follow.</p>
          <div class="result">Activity: Build a budget from a real teen scenario.</div>
        </div>
        <div class="tile">
          <h3>2) Saving & Goal Setting</h3>
          <p>Emergency funds, short vs long-term goals, and how to set weekly targets.</p>
          <div class="result">Activity: Turn a goal into a 6-week plan.</div>
        </div>
        <div class="tile">
          <h3>3) Credit & Debt</h3>
          <p>Credit scores, cards, interest, and how to avoid common debt traps.</p>
          <div class="result">Activity: “Credit card statement” challenge.</div>
        </div>
      </div>

      <div class="grid3" style="margin-top:12px;">
        <div class="tile">
          <h3>4) Investing Basics</h3>
          <p>Stocks vs ETFs, diversification, risk, and time horizon—explained simply.</p>
          <div class="result">Activity: Build a mock diversified portfolio (paper only).</div>
        </div>
        <div class="tile">
          <h3>5) Money & Mindset</h3>
          <p>Spending triggers, “quiet leaks,” and habits that make saving easier.</p>
          <div class="result">Activity: Identify your top 3 money leaks + fixes.</div>
        </div>
        <div class="tile">
          <h3>6) College & Career Money</h3>
          <p>Paychecks, taxes basics, saving from your first job, and common financial mistakes.</p>
          <div class="result">Activity: Read a paystub + plan a starter budget.</div>
        </div>
      </div>
    </section>

    <section id="partners">
      <div class="section-title">
        <div>
          <h2>Partner with us</h2>
          <p>Schools, libraries, and community groups can request a free workshop. Use the form below (demo) or link your Google Form.</p>
        </div>
      </div>

      <div class="cols">
        <div class="panel">
          <h3>Workshop request form</h3>

          <div class="row">
            <div>
              <div class="label">Organization / School</div>
              <input id="org" type="text" placeholder="Example: Lincoln High School" />
            </div>
            <div>
              <div class="label">Contact name</div>
              <input id="name" type="text" placeholder="Your name" />
            </div>
          </div>

          <div class="row">
            <div>
              <div class="label">Email</div>
              <input id="email" type="email" placeholder="name@email.com" />
            </div>
            <div>
              <div class="label">Audience</div>
              <select id="audience">
                <option value="Middle School">Middle School</option>
                <option value="High School" selected>High School</option>
                <option value="Mixed">Mixed</option>
              </select>
            </div>
          </div>

          <div class="row">
            <div>
              <div class="label">Module</div>
              <select id="module">
                <option>Budgeting Basics</option>
                <option>Saving & Goal Setting</option>
                <option>Credit & Debt</option>
                <option>Investing Basics</option>
                <option>Money & Mindset</option>
                <option>College & Career Money</option>
              </select>
            </div>
            <div>
              <div class="label">Preferred format</div>
              <select id="format">
                <option>In-person</option>
                <option>Virtual</option>
                <option>Either</option>
              </select>
            </div>
          </div>

          <div class="label">Notes (optional)</div>
          <textarea id="notes" placeholder="Dates, group size, goals, special requests..."></textarea>

          <div style="margin-top:12px;">
            <button class="btn" onclick="fakeSubmit()">Submit request</button>
          </div>

          <div id="contactResult" class="result hide"></div>

          <div class="warn">
            This demo form doesn’t send emails yet. For real messages, connect a Google Form or Formspree.
          </div>
        </div>

        <div class="panel">
          <h3>What partners receive</h3>
          <div class="result">✔ Student-friendly slide deck
✔ Hands-on activity worksheet
✔ Take-home budget template
✔ Optional pre/post “confidence” survey
✔ Follow-up resource links</div>

          <div class="tile" style="box-shadow:none; margin-top:12px;">
            <h3>Want a faster setup?</h3>
            <p>Create a Google Form and paste your link into the button below.</p>
            <a class="link" href="#" onclick="alert('Replace this with your real Google Form link!')">Open Google Form →</a>
          </div>

          <div class="tile" style="box-shadow:none; margin-top:12px;">
            <h3>Start a chapter at your school</h3>
            <p>We’ll share a club outline, meeting plan, and curriculum starter kit.</p>
            <a class="link" href="#" onclick="scrollToId('resources')">Get the Starter Kit →</a>
          </div>
        </div>
      </div>
    </section>

    <section id="resources">
      <div class="section-title">
        <div>
          <h2>Free resources</h2>
          <p>Replace the placeholder links with your Google Sheets, PDFs, or your SmartMoney AI site.</p>
        </div>
      </div>

      <div class="grid3">
        <div class="tile">
          <h3>📄 Budget Template (Google Sheet)</h3>
          <p>Simple monthly budget tracker with totals and leftover money.</p>
          <a class="link" href="#" onclick="alert('Paste your Google Sheet link here!')">Open →</a>
        </div>
        <div class="tile">
          <h3>🎯 Savings Goal Tracker</h3>
          <p>Weekly targets + progress tracker for any savings goal.</p>
          <a class="link" href="#" onclick="alert('Paste your Google Sheet link here!')">Open →</a>
        </div>
        <div class="tile">
          <h3>🤖 Safe AI Prompt Pack (PDF)</h3>
          <p>Copy/paste prompts for budgeting and saving (no risky stock-picking).</p>
          <a class="link" href="#" onclick="alert('Paste your PDF link here!')">Download →</a>
        </div>
      </div>

      <div class="cols" style="margin-top:12px;">
        <div class="panel">
          <h3>Related initiatives</h3>
          <p style="margin:0; color:var(--muted); font-weight:650;">
            If you’re running multiple programs, link them here to show a bigger ecosystem.
          </p>
          <div class="result" style="margin-top:12px;">• SmartMoney AI (tool hub)
• Youth Investment Club (paper trading + stock pitches)
• Teen Financial Literacy Lab (community workshops)</div>
          <div style="margin-top:12px;">
            <a class="link" href="#" onclick="alert('Paste your SmartMoney AI site link here!')">SmartMoney AI →</a>
          </div>
        </div>

        <div class="panel">
          <h3>Volunteer toolkit</h3>
          <div class="result">Volunteer roles:
• Workshop helper (activities + Q&A)
• Outreach (email schools/libraries)
• Curriculum (improve slides + worksheets)
• Social media (share tips + events)

We track impact:
• workshops, students, partners, volunteers</div>
          <div class="tile" style="box-shadow:none; margin-top:12px;">
            <h3>📌 Volunteer signup</h3>
            <p>Use a Google Form and paste the link here.</p>
            <a class="link" href="#" onclick="alert('Paste your volunteer form link here!')">Volunteer →</a>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="section-title">
        <div>
          <h2>About</h2>
          <p>Transparent, safe, student-friendly financial education.</p>
        </div>
      </div>

      <div class="panel">
        <p style="margin:0; color:var(--muted); font-weight:650;">
          Teen Financial Literacy Lab is a student-led initiative that delivers free, practical financial education.
          We focus on everyday skills (budgeting, saving, credit) and investing basics responsibly.
          We do not collect sensitive financial info, and we do not provide personalized investing recommendations.
        </p>

        <div class="result" style="margin-top:12px;">Values:
• Accessible: plain-language lessons and templates
• Practical: skills students can use immediately
• Responsible: no “what stock should I buy?” content
• Measurable: we track outcomes and feedback</div>
      </div>
    </section>

    <footer>
      <div class="wrap foot">
        <div>
          <div style="font-weight:950; color:var(--text);">Teen Financial Literacy Lab</div>
          <div class="small">
            Educational resources only — not financial advice. We do not collect bank logins or sensitive personal financial info.
          </div>
        </div>
        <div class="mono">
          © <span id="year"></span> • Contact: <span style="opacity:.9;">add-your-email@domain.com</span>
        </div>
      </div>
    </footer>
  </main>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();

    function scrollToId(id){
      const el = document.getElementById(id);
      if(!el) return;
      el.scrollIntoView({ behavior:"smooth", block:"start" });
    }

    // Update these numbers as you grow (edit here anytime)
    const impact = {
      workshops: 0,
      students: 0,
      partners: 0,
      volunteers: 0
    };

    document.getElementById("kpiWorkshops").textContent = impact.workshops;
    document.getElementById("kpiStudents").textContent  = impact.students;
    document.getElementById("kpiPartners").textContent  = impact.partners;
    document.getElementById("kpiVols").textContent      = impact.volunteers;

    function fakeSubmit(){
      const org = document.getElementById("org").value.trim();
      const name = document.getElementById("name").value.trim() || "there";
      const email = document.getElementById("email").value.trim();
      const audience = document.getElementById("audience").value;
      const module = document.getElementById("module").value;
      const format = document.getElementById("format").value;
      const notes = document.getElementById("notes").value.trim();

      const out = document.getElementById("contactResult");
      out.classList.remove("hide");

      if(!org || !email){
        out.textContent = "Please add your organization/school and email. (Demo form)";
        return;
      }

      let msg = "";
      msg += `Request received (demo)\n\n`;
      msg += `Organization: ${org}\n`;
      msg += `Contact: ${name}\n`;
      msg += `Email: ${email}\n`;
      msg += `Audience: ${audience}\n`;
      msg += `Module: ${module}\n`;
      msg += `Format: ${format}\n`;
      if(notes) msg += `Notes: ${notes}\n\n`;
      msg += `Next step: connect this form to Google Forms or Formspree so it sends for real.`;

      out.textContent = msg;
    }
  </script>
</body>
</html>
