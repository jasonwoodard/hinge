<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HINGE — Family Operating Model</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  @page {
    size: 8.5in 11in;
    margin: 0.25in;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Inter', sans-serif;
    background: #fff;
    color: #1E2D40;
    width: 8.5in;
    min-height: 11in;
    padding: 0.25in;
  }

  .page {
    width: 8in;
    min-height: 10.5in;
    display: flex;
    flex-direction: column;
    gap: 0.18in;
  }

  /* TITLE BLOCK */
  .title-block {
    position: relative;
    border-bottom: 2.5px solid #1E2D40;
    padding-bottom: 0.12in;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
  }

  .title-watermark {
    position: absolute;
    top: -0.05in;
    right: 0;
    font-family: 'DM Serif Display', serif;
    font-size: 72pt;
    color: #f0f0ee;
    line-height: 1;
    letter-spacing: -2px;
    user-select: none;
    pointer-events: none;
  }

  .title-left { position: relative; z-index: 1; }

  .hinge-title {
    font-family: 'DM Serif Display', serif;
    font-size: 36pt;
    color: #1E2D40;
    letter-spacing: -1px;
    line-height: 1;
  }

  .hinge-subtitle {
    font-size: 8pt;
    color: #6B7D8F;
    margin-top: 3px;
    letter-spacing: 0.5px;
    text-transform: uppercase;
  }

  .hinge-tagline {
    font-size: 9pt;
    color: #1E2D40;
    font-style: italic;
    text-align: right;
    position: relative;
    z-index: 1;
  }

  /* PRIMARY DEFINITION */
  .primary-def {
    background: #1E2D40;
    color: #fff;
    padding: 0.12in 0.15in;
    border-radius: 4px;
    display: flex;
    align-items: center;
    gap: 0.15in;
  }

  .primary-label {
    font-family: 'DM Serif Display', serif;
    font-size: 22pt;
    color: #E8933A;
    white-space: nowrap;
    line-height: 1;
  }

  .primary-pipe {
    width: 1.5px;
    height: 36px;
    background: rgba(255,255,255,0.2);
    flex-shrink: 0;
  }

  .primary-text {
    font-size: 8pt;
    line-height: 1.55;
    color: rgba(255,255,255,0.88);
  }

  /* PRINCIPLES */
  .principles-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0.1in;
  }

  .principle-card {
    border: 1px solid #E0E4E8;
    border-radius: 4px;
    padding: 0.1in;
  }

  .principle-title {
    font-size: 7.5pt;
    font-weight: 600;
    color: #1E2D40;
    margin-bottom: 3px;
    text-transform: uppercase;
    letter-spacing: 0.4px;
  }

  .principle-text {
    font-size: 7pt;
    color: #4A5568;
    line-height: 1.5;
  }

  /* SECTION LABEL */
  .section-label {
    font-size: 7pt;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: #9BAAB8;
    margin-bottom: 0.06in;
  }

  /* WEEK TABLES */
  .weeks-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.15in;
  }

  .week-block { display: flex; flex-direction: column; gap: 6px; }

  .week-header {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .week-badge {
    font-family: 'DM Serif Display', serif;
    font-size: 13pt;
    color: #1E2D40;
    line-height: 1;
  }

  .week-iso {
    font-size: 7pt;
    color: #9BAAB8;
    font-style: italic;
  }

  .week-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 7.5pt;
  }

  .week-table th {
    background: #1E2D40;
    color: rgba(255,255,255,0.75);
    text-align: center;
    padding: 4px 3px;
    font-weight: 500;
    font-size: 6.5pt;
    letter-spacing: 0.3px;
  }

  .week-table td {
    text-align: center;
    padding: 5px 3px;
    font-size: 7.5pt;
    border: 1px solid #E8ECF0;
  }

  .row-label {
    text-align: left !important;
    font-weight: 600;
    font-size: 6.5pt;
    color: #6B7D8F;
    text-transform: uppercase;
    letter-spacing: 0.3px;
    padding-left: 5px !important;
    background: #F8F9FA;
    white-space: nowrap;
  }

  .cell-Parent 2 {
    background: #DEEEF8;
    color: #0C4472;
    font-weight: 500;
  }

  .cell-Parent 1 {
    background: #FDEBD0;
    color: #7A4010;
    font-weight: 500;
  }

  .cell-family {
    background: #E8F4EC;
    color: #1A5C2E;
    font-weight: 500;
    font-style: italic;
    font-size: 6.5pt;
  }

  .cell-open {
    background: #F8F9FA;
    color: #9BAAB8;
    font-size: 6.5pt;
  }

  .week-note {
    font-size: 6.5pt;
    color: #9BAAB8;
    font-style: italic;
    margin-top: 2px;
  }

  /* LEGEND */
  .legend {
    display: flex;
    gap: 0.15in;
    align-items: center;
  }

  .legend-item {
    display: flex;
    align-items: center;
    gap: 5px;
    font-size: 7pt;
    color: #4A5568;
  }

  .legend-swatch {
    width: 12px;
    height: 12px;
    border-radius: 2px;
    flex-shrink: 0;
  }

  /* BOTTOM ROW */
  .bottom-row {
    display: grid;
    grid-template-columns: 1.1fr 1fr;
    gap: 0.15in;
    flex: 1;
  }

  /* CATEGORICALS */
  .cat-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 7pt;
  }

  .cat-table th {
    background: #1E2D40;
    color: rgba(255,255,255,0.75);
    text-align: left;
    padding: 4px 6px;
    font-weight: 500;
    font-size: 6.5pt;
    letter-spacing: 0.3px;
    text-transform: uppercase;
  }

  .cat-table td {
    padding: 4px 6px;
    border-bottom: 1px solid #EEF0F2;
    vertical-align: top;
    line-height: 1.4;
    color: #2D3748;
  }

  .cat-table tr:nth-child(even) td { background: #F8F9FA; }

  .cat-name { font-weight: 500; color: #1E2D40; }

  /* NUMBERS */
  .numbers-block { display: flex; flex-direction: column; gap: 0.1in; }

  .numbers-title {
    font-family: 'DM Serif Display', serif;
    font-size: 11pt;
    color: #1E2D40;
  }

  .stat-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.08in;
  }

  .stat-card {
    border: 1px solid #E0E4E8;
    border-radius: 4px;
    padding: 0.08in 0.1in;
  }

  .stat-number {
    font-family: 'DM Serif Display', serif;
    font-size: 20pt;
    color: #1E2D40;
    line-height: 1;
  }

  .stat-label {
    font-size: 6.5pt;
    color: #9BAAB8;
    text-transform: uppercase;
    letter-spacing: 0.4px;
    margin-top: 2px;
  }

  .iso-explainer {
    background: #F8F9FA;
    border-left: 3px solid #E8933A;
    padding: 0.08in 0.1in;
    border-radius: 0 4px 4px 0;
  }

  .iso-title {
    font-size: 7.5pt;
    font-weight: 600;
    color: #1E2D40;
    margin-bottom: 3px;
  }

  .iso-rule {
    font-size: 7pt;
    color: #4A5568;
    line-height: 1.5;
  }

  .iso-rule strong {
    color: #1E2D40;
    font-weight: 600;
  }

  .swap-block {
    border: 1px solid #E0E4E8;
    border-radius: 4px;
    padding: 0.08in 0.1in;
  }

  .swap-title {
    font-size: 7.5pt;
    font-weight: 600;
    color: #1E2D40;
    margin-bottom: 3px;
  }

  .swap-text {
    font-size: 7pt;
    color: #4A5568;
    line-height: 1.5;
  }

  /* FOOTER */
  .footer {
    border-top: 1px solid #E0E4E8;
    padding-top: 0.08in;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .footer-left {
    font-family: 'DM Serif Display', serif;
    font-size: 8pt;
    color: #9BAAB8;
  }

  .footer-right {
    font-size: 6.5pt;
    color: #C0C8D0;
    font-style: italic;
  }
</style>
</head>
<body>
<div class="page">

  <!-- TITLE -->
  <div class="title-block">
    <div class="title-watermark">PRIMARY</div>
    <div class="title-left">
      <div class="hinge-title">HINGE</div>
      <div class="hinge-subtitle">Household Implicit Negotiation-free Grace Endeavor</div>
    </div>
    <div class="hinge-tagline">Not a chore chart.<br>An operating agreement.</div>
  </div>

  <!-- PRIMARY DEFINITION -->
  <div class="primary-def">
    <div class="primary-label">Primary</div>
    <div class="primary-pipe"></div>
    <div class="primary-text">
      HINGE answers one question every day: <em>which parent is Primary today?</em> The Primary parent owns the day end to end — morning launch, afternoon pickup, after-school obligations, and whatever comes up in between. The other parent is present and available but not on point. They have the day. This single distinction, clearly assigned and known in advance, is what makes everything else work.
    </div>
  </div>

  <!-- PRINCIPLES -->
  <div>
    <div class="section-label">Principles</div>
    <div class="principles-grid">
      <div class="principle-card">
        <div class="principle-title">Blocks matter</div>
        <div class="principle-text">Two or more contiguous free days every week. Not scattered hours — momentum.</div>
      </div>
      <div class="principle-card">
        <div class="principle-title">Equity is structural</div>
        <div class="principle-text">Fairness is baked into the pattern. Over any two-week cycle, both parents carry exactly equal primary days.</div>
      </div>
      <div class="principle-card">
        <div class="principle-title">Grace is the coverage rule</div>
        <div class="principle-text">When one parent is unavailable, the other absorbs it. No log, no IOU, no rebalancing conversation.</div>
      </div>
      <div class="principle-card">
        <div class="principle-title">Always knowable</div>
        <div class="principle-text">Any day, months from now, has a named Primary. Book appointments and plan with confidence.</div>
      </div>
    </div>
  </div>

  <!-- WEEK TABLES -->
  <div>
    <div class="section-label">The pattern — fortnightly rotation</div>
    <div class="weeks-row">

      <div class="week-block">
        <div class="week-header">
          <div class="week-badge">Week A</div>
          <div class="week-iso">Odd ISO week number</div>
        </div>
        <table class="week-table">
          <thead>
            <tr>
              <th style="width:52px"></th>
              <th>Mon</th><th>Tue</th><th>Wed</th><th>Thu</th><th>Fri</th><th>Sat*</th><th>Sun</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td class="row-label">Primary</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-open">—</td>
            </tr>
            <tr>
              <td class="row-label">Available</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-family">Both</td>
            </tr>
          </tbody>
        </table>
        <div class="week-note">Parent 2 free block: Thu–Fri &nbsp;·&nbsp; Parent 1 free block: Mon–Tue</div>
      </div>

      <div class="week-block">
        <div class="week-header">
          <div class="week-badge">Week B</div>
          <div class="week-iso">Even ISO week number</div>
        </div>
        <table class="week-table">
          <thead>
            <tr>
              <th style="width:52px"></th>
              <th>Mon</th><th>Tue</th><th>Wed</th><th>Thu</th><th>Fri</th><th>Sat*</th><th>Sun</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td class="row-label">Primary</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-open">—</td>
            </tr>
            <tr>
              <td class="row-label">Available</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 2">Parent 2</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-Parent 1">Parent 1</td>
              <td class="cell-family">Both</td>
            </tr>
          </tbody>
        </table>
        <div class="week-note">Parent 1 free block: Thu–Fri &nbsp;·&nbsp; Parent 2 free block: Mon–Tue</div>
      </div>

    </div>

    <div style="display:flex; align-items:center; gap:0.2in; margin-top:0.07in;">
      <div class="legend">
        <div class="legend-item"><div class="legend-swatch" style="background:#DEEEF8;border:1px solid #B5D4F4"></div> Parent 2 primary</div>
        <div class="legend-item"><div class="legend-swatch" style="background:#FDEBD0;border:1px solid #FAC775"></div> Parent 1 primary</div>
        <div class="legend-item"><div class="legend-swatch" style="background:#E8F4EC;border:1px solid #C0DD97"></div> Both present</div>
      </div>
      <div style="font-size:6.5pt; color:#9BAAB8; font-style:italic;">* Saturday Primary follows from Friday — whoever owned Friday carries the day.</div>
    </div>
  </div>

  <!-- BOTTOM ROW -->
  <div class="bottom-row">

    <!-- CATEGORICALS -->
    <div>
      <div class="section-label">Categoricals — handled by rule, not negotiation</div>
      <table class="cat-table">
        <thead>
          <tr>
            <th style="width:30%">Situation</th>
            <th>How HINGE handles it</th>
          </tr>
        </thead>
        <tbody>
          <tr><td><span class="cat-name">School holiday</span></td><td>Primary parent's day is fuller. Pattern unchanged.</td></tr>
          <tr><td><span class="cat-name">Half day / early dismissal</span></td><td>Primary adjusts pickup time. Pattern unchanged.</td></tr>
          <tr><td><span class="cat-name">Child sick day</span></td><td>Whoever is Primary that day owns it. Rotates normally.</td></tr>
          <tr><td><span class="cat-name">Parent unavailable</span></td><td>Other parent absorbs. No tracking. Grace.</td></tr>
          <tr><td><span class="cat-name">Multi-day travel</span></td><td>Other parent covers all affected days. Coverage rule applies.</td></tr>
          <tr><td><span class="cat-name">School event, one parent</span></td><td>Primary attends naturally. Rotates across the cycle.</td></tr>
          <tr><td><span class="cat-name">School event, both parents</span></td><td>Both show up. Primary suspended for the event.</td></tr>
          <tr><td><span class="cat-name">Saturday categorical</span></td><td>Friday owner handles it — already Primary.</td></tr>
          <tr><td><span class="cat-name">Sunday categorical</span></td><td>Saturday Primary handles it. Other parent gets the free window.</td></tr>
        </tbody>
      </table>
    </div>

    <!-- RIGHT COLUMN -->
    <div class="numbers-block">

      <div class="section-label">By the numbers — full school year</div>
      <div class="stat-grid">
        <div class="stat-card">
          <div class="stat-number">102</div>
          <div class="stat-label">Primary weekdays each</div>
        </div>
        <div class="stat-card">
          <div class="stat-number">~20</div>
          <div class="stat-label">Saturday afternoons each</div>
        </div>
        <div class="stat-card">
          <div class="stat-number">20</div>
          <div class="stat-label">3-day primary weeks each</div>
        </div>
        <div class="stat-card">
          <div class="stat-number">20</div>
          <div class="stat-label">2-day primary weeks each</div>
        </div>
      </div>

      <div class="iso-explainer">
        <div class="iso-title">Looking up any future day</div>
        <div class="iso-rule">
          1. Find the ISO week number (any calendar app).<br>
          <strong>Odd week = Week A</strong> (Parent 2 Mon–Wed, Parent 1 Thu–Fri)<br>
          <strong>Even week = Week B</strong> (Parent 1 Mon–Wed, Parent 2 Thu–Fri)<br>
          2. Done. No lookup table needed.
        </div>
      </div>

      <div class="swap-block">
        <div class="swap-title">Swapping</div>
        <div class="swap-text">The default answer to a swap request is <em>yes, of course.</em> A swap is not a withdrawal — it is an expression of the grace that underlies the whole system. No rebalancing conversation needed. Communicate early as a courtesy, not a rule.</div>
      </div>

    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-left">HINGE</div>
    <div class="footer-right">Not a chore chart. An operating agreement.</div>
  </div>

</div>
</body>
</html>
