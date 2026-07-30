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

<div class="eyebrow">A reading guide</div>

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

<div class="eyebrow">The two rules</div>

## Read down.<br>Never across.

<div class="rules">
<div class="rule-card">
  <span class="rule-n">Rule one</span>
  <p class="rule-h">Don't compare across categories.</p>
  <p class="rule-b">43.3% on coding and 11.7% on legal are not on the same scale. The gap says nothing about relative ability — it says the two benchmarks were built to different specifications.</p>
</div>
<div class="rule-card alt">
  <span class="rule-n">Rule two</span>
  <p class="rule-h">Compare across models on one row — if the version held.</p>
  <p class="rule-b">Same benchmark, different models is the one valid comparison. But ARC-AGI-3 changed its scoring in April 2026; scores do not cross that line.</p>
</div>
</div>

---

<div class="wm">04</div>

<div class="eyebrow">Vocabulary</div>

## Three ways to earn a number

<div class="paradigms">
  <div class="para">
    <span class="para-n">1</span>
    <span class="para-t">Binary pass / fail</span>
    <span class="para-d">Run it. Did it work?</span>
    <span class="para-w">Frontier-Bench · DeepSWE</span>
  </div>
  <div class="para">
    <span class="para-n">2</span>
    <span class="para-t">Efficiency ratio</span>
    <span class="para-d">How many steps, against a human baseline?</span>
    <span class="para-w">ARC-AGI-3</span>
  </div>
  <div class="para">
    <span class="para-n">3</span>
    <span class="para-t">Rubric</span>
    <span class="para-d">Check a written list, item by item.</span>
    <span class="para-w">FrontierCode · HealthBench · Legal Agent Bench</span>
  </div>
</div>

<div class="callout">
  <p class="callout-l">The trap</p>
  <p>A rubric score and a pass rate are not the same kind of number. 53.4% on FrontierCode is an <strong>average rubric score</strong>; 68.8% on DeepSWE is a <strong>share of tasks solved</strong>.</p>
</div>

---

<div class="wm">05</div>

<div class="eyebrow">Category 01</div>

## Coding

| Benchmark | Example task | Scored by |
|---|---|---|
| Frontier-Bench | "The DB migration is broken — get `pytest` passing." Full shell access. | Harness re-runs the check itself. Binary, mean over 5 runs. |
| DeepSWE | "Add exponential-backoff retry: 1s/2s/4s/8s/16s, then fail." Written from scratch to resist contamination. | Hand-written test asserts real retry behaviour. Binary. |
| FrontierCode | "Fix a race condition in the job queue." | **Blockers** (fixed · no regression · scoped) are gates — miss one and the task scores 0. Style and quality are LLM-reviewed and weighted in after. |

<div class="callout">
  <p class="callout-l">The hidden variable</p>
  <p>None of these test a bare model — they test a model <strong>plus a harness</strong>. A tuned harness against a bare shell can move the same model by 10+ points.</p>
</div>

---

<div class="wm">06</div>

<div class="eyebrow">Category 02</div>

## Novel problem-solving

<div class="split">
<div>
  <p class="lede-sm">No instructions, no tutorial. The model is dropped into a game and must infer the rules, the goal, and the win condition by acting.</p>

  <div class="formula">score = min(1.15, (human steps ÷ AI steps)<sup>2</sup>)</div>
  <p class="cap">Squared — so being twice as slow as a human costs 75% of the points, not 50%. The baseline is the median first-time player.</p>

  <div class="callout" style="margin-top:14px">
    <p class="callout-l">Opus 5 scores 30.2% overall — which means what?</p>
    <p>Averaged over 25 games, so it hides two failure modes. <strong>Cleared everything but took ~1.8× the human steps</strong> → (1÷1.8)² ≈ 31%. Or <strong>human-efficient but only ~30% of levels cleared</strong> → 30%. Reality is a blend.</p>
  </div>
</div>
<div>
  <div class="figure">
    <img src="/arc-agi-3.png" alt="ARC-AGI-3 task ls20 gameplay">
  </div>
  <p class="cap">ARC-AGI-3, task <strong>ls20</strong> — playable at arcprize.org. The only benchmark on the table that has not saturated.</p>
  <div class="stats" style="margin-top:14px">
    <div>
      <div class="stat-v">100<span class="u">%</span></div>
      <div class="stat-l">Humans on ls20, in 776 actions</div>
    </div>
    <div>
      <div class="stat-v clay">5.36<span class="u">%</span></div>
      <div class="stat-l">Opus 5 on that same task</div>
    </div>
  </div>
</div>
</div>

---

<div class="wm">07</div>

<div class="eyebrow">Category 03</div>

## Knowledge work

<p class="lede-sm">There is no score anywhere in this pipeline. Every number comes from one model's work being preferred over another's.</p>

<div class="pipeline">
  <div class="step">
    <span class="step-n">Step 01 · Source</span>
    <p class="step-h">Real professional deliverables</p>
    <p class="step-b">Tasks drawn from <em>44 occupations across 9 industries</em> — finance, healthcare, legal, engineering — written by practitioners averaging 14 years' experience.</p>
  </div>
  <div class="step">
    <span class="step-n">Step 02 · Attempt</span>
    <p class="step-h">The model does the job</p>
    <p class="step-b">An agentic sandbox (Stirrup) with web search, code execution and a filesystem, up to <em>250 turns</em>. It ships real documents, slides and spreadsheets.</p>
  </div>
  <div class="step">
    <span class="step-n">Step 03 · Judge</span>
    <p class="step-h">Blind pairwise, one judge per matchup</p>
    <p class="step-b">Two outputs for the <em>same task</em> are anonymised and set side by side. A judge picks a winner — sampled each time from a panel of three frontier LLMs.</p>
  </div>
  <div class="step">
    <span class="step-n">Step 04 · Rating</span>
    <p class="step-h">Fitted into an Elo scale</p>
    <p class="step-b">Thousands of matchups are fitted with a Bradley–Terry model, then <em>anchored so human expert = 1000</em>. No ceiling.</p>
  </div>
</div>

<div class="split" style="margin-top:20px">
<div>
  <div class="formula formula-sm">
    P(win) =
    <span class="frac"><span class="num">1</span><span class="den">1 + 10<sup>−Δ⁄400</sup></span></span>
  </div>
  <p class="cap">Opus 5 scores <strong>1861</strong>. Against the 1000 anchor, Δ = 861 — roughly a <strong>99%</strong> win rate head-to-head against the human deliverable.</p>
</div>
<div>
  <div class="callout" style="margin-top:0">
    <p class="callout-l">Who is holding the ruler</p>
    <p>The panel is <strong>GPT-5.5, Gemini 3.1 Pro and Claude Opus 4.8</strong> — so one judge comes from the same lab as the model topping this row. And LLM judges reliably prefer polished, well-structured writing over the terse, shorthand-heavy work real experts actually deliver.</p>
  </div>
</div>
</div>

<p class="tagline" style="margin-top:16px;font-size:19px">1861 means “this looks like expert work to an LLM” — not “this replaces experts.”</p>

---

<div class="wm">08</div>

<div class="eyebrow">Category 04</div>

## Agentic search

<p class="lede">Answers that are fixed but genuinely hard to find — multi-round retrieval, then cross-verification.</p>

<div class="stats" style="margin-top:30px">
  <div>
    <div class="stat-v clay">90.8<span class="u">%</span></div>
    <div class="stat-l">Opus 5</div>
  </div>
  <div>
    <div class="stat-v">90.4<span class="u">%</span></div>
    <div class="stat-l">GPT-5.6 Sol</div>
  </div>
  <div>
    <div class="stat-v">0.4<span class="u">pp</span></div>
    <div class="stat-l">The entire gap</div>
  </div>
</div>

<div style="height:1px;background:var(--rule);margin:32px 0"></div>

<p class="tagline">Past 90%, a benchmark stops separating models. Keep it to catch regressions — not to measure progress.</p>

---

<div class="wm">09</div>

<div class="eyebrow">Category 05</div>

## Long chains, no partial credit

<div class="split">
<div>
  <p class="lede-sm">Flag at-risk customers → notify the owners → write the report. Every step must be right; one failure scores the whole task zero.</p>
  <div class="stats">
    <div>
      <div class="stat-v clay">11.7<span class="u">%</span></div>
      <div class="stat-l">Legal Agent Benchmark</div>
    </div>
    <div>
      <div class="stat-v clay">26.0<span class="u">%</span></div>
      <div class="stat-l">AutomationBench</div>
    </div>
  </div>
  <p class="cap">11.7% is the probability that <strong>every</strong> criterion passed — not that 11.7% of the work got done.</p>
</div>
<div>
  <div class="callout" style="margin-top:0">
    <p class="callout-l">The failure mode that matters</p>
    <p><strong>72–91% of failures</strong> are the agent reporting success while the world state is actually wrong.</p>
  </div>
  <p class="tagline" style="margin-top:20px;font-size:19px">That is a self-verification gap, not a capability gap — and it is worse, because nothing raises an error.</p>
</div>
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

<div class="kicker">
  <p class="kicker-q">Whoever holds the ruler decides the answer.</p>
  <p class="kicker-b">ARC-AGI-3 says humans beat the best model 100% to 30.2%. GDPval-AA says the same model beats human experts 99 times out of 100. Same table, opposite verdicts — and the entire difference is methodology.</p>
</div>
