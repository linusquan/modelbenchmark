---
theme: default
title: Reading the Benchmark Table
info: How to interpret model evaluation scores — and what the July 2026 frontier comparison actually says.
canvasWidth: 1100
fonts:
  sans: Instrument Sans
  serif: Fraunces
  provider: google
transition: fade
drawings:
  persist: false
mdc: true
---

<div class="wm">01</div>

<div class="eyebrow">Reading guide</div>

# Reading the<br>Benchmark Table

<div class="lede" style="margin-top:26px">
How to interpret model evaluation scores — and what the July 2026 frontier comparison actually says once you know what each number means.
</div>

<div class="foot">Source table: Claude Opus 5 System Card, 24 July 2026</div>

---

<div class="wm">02</div>

<div class="split-fig">
<div>
  <div class="eyebrow">The artifact</div>
  <h2 style="margin-bottom:14px">One table,<br>twelve rulers</h2>
  <p class="lede-sm">Every row is scored by a different system. That single fact is the source of nearly every misreading.</p>
</div>
<div class="figure figure-tall">
  <img src="/benchmark-table.png" alt="Benchmark comparison table">
</div>
</div>

---

<div class="wm">03</div>

<div class="eyebrow">The landscape</div>

## Six categories

<p class="lede-sm" style="max-width:74ch">Every row in the table belongs to one of six categories. What a score means depends entirely on which one it came from.</p>

<div class="land">
  <div class="land-card">
    <span class="land-k">01</span>
    <p class="land-h">Software coding</p>
    <p class="land-d">Fix, build and ship inside a real shell.</p>
    <p class="land-w">Frontier-Bench · DeepSWE · FrontierCode</p>
  </div>
  <div class="land-card">
    <span class="land-k">02</span>
    <p class="land-h">Knowledge work</p>
    <p class="land-d">Office deliverables from 44 professions, judged blind.</p>
    <p class="land-w">GDPval-AA</p>
  </div>
  <div class="land-card">
    <span class="land-k">03</span>
    <p class="land-h">Dedicated professions</p>
    <p class="land-d">Licensed-domain work — law, medicine, biology.</p>
    <p class="land-w">Legal Agent Benchmark · HealthBench Pro · BioMysteryBench</p>
  </div>
  <div class="land-card">
    <span class="land-k">04</span>
    <p class="land-h">Novel reasoning</p>
    <p class="land-d">Questions built so no training run has seen them.</p>
    <p class="land-w">ARC-AGI-3 · Humanity's Last Exam</p>
  </div>
  <div class="land-card">
    <span class="land-k">05</span>
    <p class="land-h">Info search</p>
    <p class="land-d">Answers that are fixed but genuinely hard to find.</p>
    <p class="land-w">BrowseComp</p>
  </div>
  <div class="land-card">
    <span class="land-k">06</span>
    <p class="land-h">Computer use & workflows</p>
    <p class="land-d">Operate real software — long chains, no partial credit.</p>
    <p class="land-w">OSWorld 2.0 · AutomationBench</p>
  </div>
</div>

<p class="cap" style="margin-top:16px">The table's own category labels, consolidated from twelve rows.</p>

---
layout: default
class: dense
---

<div class="wm">04</div>

<div class="eyebrow">The methods</div>

<h2 style="margin-bottom:6px">How each one is marked</h2>

<table class="matrix">
<thead><tr>
  <th>Category</th><th>Benchmark</th>
  <th class="n">Binary<br>pass / fail</th>
  <th class="n">Rubric<br>scored</th>
  <th class="n">Human<br>baseline</th>
  <th class="n">LLM<br>judge</th>
</tr></thead>
<tbody>
<tr class="grp"><td class="cat">Coding</td><td>Frontier-Bench</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g0">—</td><td class="n g0">—</td></tr>
<tr><td></td><td>DeepSWE</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g0">—</td><td class="n g0">—</td></tr>
<tr><td></td><td>FrontierCode</td><td class="n g2">◐</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g1">●</td></tr>
<tr class="grp"><td class="cat">Knowledge work</td><td>GDPval-AA</td><td class="n g0">—</td><td class="n g0">—</td><td class="n g1">●</td><td class="n g1">●</td></tr>
<tr class="grp"><td class="cat">Professions</td><td>Legal Agent Bench</td><td class="n g2">◐</td><td class="n g1">●</td><td class="n g0">—</td><td class="n gq">?</td></tr>
<tr><td></td><td>HealthBench Pro</td><td class="n g0">—</td><td class="n g1">●</td><td class="n g2">◐</td><td class="n g1">●</td></tr>
<tr><td></td><td>BioMysteryBench</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g1">●</td><td class="n g0">—</td></tr>
<tr class="grp"><td class="cat">Novel reasoning</td><td>ARC-AGI-3</td><td class="n g2">◐</td><td class="n g0">—</td><td class="n g1">●</td><td class="n g0">—</td></tr>
<tr><td></td><td>Humanity's Last Exam</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g0">—</td><td class="n g2">◐</td></tr>
<tr class="grp"><td class="cat">Info search</td><td>BrowseComp</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g2">◐</td><td class="n g2">◐</td></tr>
<tr class="grp"><td class="cat">Computer use</td><td>OSWorld 2.0</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g0">—</td><td class="n g0">—</td></tr>
<tr><td></td><td>AutomationBench</td><td class="n g1">●</td><td class="n g0">—</td><td class="n g1">●</td><td class="n g0">—</td></tr>
</tbody>
</table>

<div class="legend">
  <b><span class="g1">●</span> primary method</b>
  <b><span class="g2">◐</span> partial / secondary</b>
  <b><span class="g0">—</span> not used</b>
  <b><span class="gq">?</span> not published</b>
</div>

<div class="callout" style="margin-top:9px;padding:9px 14px">
  <p class="callout-l" style="margin-bottom:4px">What a rubric actually is</p>
  <p style="font-size:11.5px;line-height:1.4">A human-written checklist of criteria for one task — <em>"cites a real statute · flags the limitation period · no invented case law."</em> Something walks the list and awards points per criterion met — usually another LLM, which is why the two right-hand columns overlap. <strong>Binary asks "did it run?" A rubric asks "is it any good?" — only the first has a machine-checkable answer.</strong></p>
</div>

---

<div class="wm">05</div>

<div class="eyebrow">Tolerance</div>

## One mistake, different cost

<p class="lede-sm" style="max-width:70ch">Coding benchmarks don't score gently because they're coding — most just test one thing per task. The real variable is how many gates a task has to clear.</p>

<div class="pipeline" style="grid-template-columns:repeat(3,1fr);margin-top:26px">
  <div class="step">
    <span class="step-n">Single gate · Frontier-Bench</span>
    <p class="step-h">Nothing to compound</p>
    <p class="step-b">One check: does <code>pytest</code> pass? A near-miss and a clean fix score the same as long as the test goes green.</p>
  </div>
  <div class="step">
    <span class="step-n">Short chain · FrontierCode</span>
    <p class="step-h">Any one blocker zeroes it</p>
    <p class="step-b">Fixed · no regression · scoped — all three must clear. Nail two of three and the task still scores 0.</p>
  </div>
  <div class="step">
    <span class="step-n">Long chain · AutomationBench, Legal</span>
    <p class="step-h">Compounding, not additive</p>
    <p class="step-b">Flag → notify → report. Every step must land. The further the chain runs, the more a single slip costs.</p>
  </div>
</div>

<div class="callout" style="margin-top:20px">
  <p class="callout-l">The math behind it</p>
  <p>A model right <strong>95% of the time per step</strong> scores 95% on a single-gate task, ~86% on a short 3-step chain, and ~36% on a 20-step chain — same underlying reliability, wildly different numbers. Legal Agent Benchmark's 11.7% isn't a weaker model; it's a longer chain.</p>
</div>

---

<div class="wm">06</div>

<div class="eyebrow">Coding</div>

## Coding

| Benchmark | Example task |
|---|---|
| Frontier-Bench | **Full shell, no scaffolding.** "Production deploy is broken — SSH in, find what regressed, get the health check green again." |
| DeepSWE | **Invented, not an adapted PR.** "Implement a token-bucket rate limiter with three custom edge cases" — no existing GitHub fix to recall. |
| FrontierCode | **Judged, not just run.** "Fix a race condition in the job queue" — a blanket lock 'solves' it but fails the no-regression and scope gates. |

<div class="callout">
  <p class="callout-l">The hidden variable</p>
  <p>None of these test a bare model — they test a model <strong>plus a harness</strong>. A tuned harness against a bare shell can move the same model by 10+ points.</p>
</div>

---

<div class="wm">07</div>

<div class="eyebrow">Reasoning</div>

## Novel problem-solving

<div class="split">
<div>
  <p class="lede-sm">No instructions. The model is dropped into a game and must figure out the rules by acting — then it's scored on how many steps it needed, against a human baseline.</p>

  <div class="formula">score = min(1.15, (human steps ÷ AI steps)<sup>2</sup>)</div>
  <p class="cap">Match the human pace, score 100%. Take twice as long, score ~25% — not 50%, because the gap is squared.</p>

  <div class="stats" style="margin-top:20px">
    <div>
      <div class="stat-v">100<span class="u">%</span></div>
      <div class="stat-l">Human baseline, by definition</div>
    </div>
    <div>
      <div class="stat-v clay">30.2<span class="u">%</span></div>
      <div class="stat-l">Opus 5, averaged over 25 games</div>
    </div>
  </div>
</div>
<div>
  <div class="figure">
    <img src="/arc-agi-3.png" alt="ARC-AGI-3 task ls20 gameplay">
  </div>
  <p class="cap">ARC-AGI-3, task <strong>ls20</strong> — playable at arcprize.org. The only benchmark on the table that has not saturated.</p>
</div>
</div>

---

<div class="wm">08</div>

<div class="eyebrow">Generic problems</div>

## Knowledge work

<p class="lede-sm">There is no score anywhere in this pipeline. Every number comes from one model's work being preferred over another's.</p>

<div class="pipeline">
  <div class="step">
    <span class="step-n">01 · Source</span>
    <p class="step-h">Real professional work</p>
    <p class="step-b">Tasks from <em>44 occupations</em>, written by practitioners.</p>
  </div>
  <div class="step">
    <span class="step-n">02 · Attempt</span>
    <p class="step-h">The model does the job</p>
    <p class="step-b">An agentic sandbox ships real documents and spreadsheets.</p>
  </div>
  <div class="step">
    <span class="step-n">03 · Judge</span>
    <p class="step-h">Blind, side by side</p>
    <p class="step-b">Model output vs. human output — an LLM picks the winner.</p>
  </div>
  <div class="step">
    <span class="step-n">04 · Rating</span>
    <p class="step-h">Fitted into an Elo scale</p>
    <p class="step-b">Win/loss record converted to a score, <em>human expert = 1000</em>.</p>
  </div>
</div>

<div class="callout" style="margin-top:20px">
  <p class="callout-l">Opus 5 scores 1861 — a 99% win rate against the human deliverable, head-to-head</p>
  <p>But the judge panel includes <strong>Claude Opus 4.8</strong>, from the same lab as the model topping this row — and LLM judges reliably favour polished, well-structured writing over the terse, shorthand-heavy work real experts actually deliver.</p>
</div>

<p class="tagline" style="margin-top:16px;font-size:19px">1861 means “this looks like expert work to an LLM” — not “this replaces experts.”</p>

---

<div class="wm">09</div>

<div class="eyebrow">The instrument</div>

## Every benchmark carries systematic error

<p class="lede-sm" style="max-width:74ch">Even a number that is honestly reported and fairly compared was produced by something with known defects. Four stages, four failure modes.</p>

<div class="pipeline">
  <div class="step">
    <span class="step-n">01 · The questions</span>
    <p class="step-h">Coaching looks like ability</p>
    <p class="step-b">Like a student whose tutor drilled thousands of practice papers in exactly this style. They <em>never saw the real exam</em> — and can say so honestly. The score still goes up. From outside, coaching and real ability look the same.</p>
  </div>
  <div class="step">
    <span class="step-n">02 · The answer key</span>
    <p class="step-h">The ground truth can be wrong</p>
    <p class="step-b"><em>~29%</em> of HLE's bio/chem answers conflict with published literature. Questions were admitted only if frontier models failed them, with a 5-minute review cap — selecting for "stumps the AI" selects for broken questions.</p>
  </div>
  <div class="step">
    <span class="step-n">03 · The scorer</span>
    <p class="step-h">Judges and rewards leak</p>
    <p class="step-b">LLM judges reward length and polish over correctness. Even <em>deterministic</em> scoring leaks — Zapier watched agents hold their reward while API calls fell to near zero.</p>
  </div>
  <div class="step">
    <span class="step-n">04 · The reporting</span>
    <p class="step-h">Composites hide regressions</p>
    <p class="step-b">Indices net sub-scores against each other — #1 on AA-Omniscience hallucinates <em>more</em> than #2. The metric that exposes it, calibration error, goes uncited by every vendor.</p>
  </div>
</div>

<div class="callout" style="margin-top:16px">
  <p class="callout-l">What survives</p>
  <p>And any published benchmark gets scraped into the next model's training data — so it wears out with age, however well it was built. Only the ones holding a <strong>private set of questions back</strong> resist that: ARC-AGI-3, AutomationBench, Legal Agent Benchmark.</p>
</div>

---

<div class="wm">10</div>

<div class="eyebrow">What the data says</div>

## Four conclusions

<div class="concl">
  <div class="c-item">
    <span class="c-k">A</span>
    <span class="c-h">Coding has converged — the differentiator moved.</span>
    <span class="c-b">On DeepSWE, Opus 5 places third (GPT-5.6 Sol 72.7% · Fable 5 69.7% · Opus 5 68.8%). On FrontierCode the top two sit 0.1pp apart — noise, not a result. The one coding row with a real gap is Frontier-Bench, the bare-terminal one. Writing a correct patch is commoditised; operating without scaffolding is not.</span>
  </div>
  <div class="c-item">
    <span class="c-k">B</span>
    <span class="c-h">The wall is compounding error, not difficulty.</span>
    <span class="c-b">95% reliability per step across 20 steps leaves 36%. Most of the low workflow scores are all-or-nothing grading meeting long chains — and the dominant failure is the agent not knowing it failed.</span>
  </div>
  <div class="c-item">
    <span class="c-k">C</span>
    <span class="c-h">Progress is fastest on reasoning, slowest on professional reliability.</span>
    <span class="c-b">Opus 4.8 → Opus 5: ARC-AGI-3 went 1.5% → 30.2%, a 20× jump. Over the same generation, Legal moved 10.4% → 11.7% and Health 57.4% → 59.8%. Novel reasoning is moving; domain reliability is barely budging.</span>
  </div>
  <div class="c-item">
    <span class="c-k">D</span>
    <span class="c-h">There is no “best model” — the leader changes by row.</span>
    <span class="c-b">GPT-5.6 Sol takes DeepSWE, Fable 5 takes FrontierCode and Legal, Mythos 5 takes Health. And specialisation is sharp: GPT-5.6 Sol scores 2.5% on Legal against Opus 5's 11.7% — 4.7× worse on one row while winning another.</span>
  </div>
</div>
