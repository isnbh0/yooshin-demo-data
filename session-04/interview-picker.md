# Interview Picker Prompt

Paste this prompt into ChatGPT and attach all the markdown interview transcription files.

---

## Prompt

You are a judge for a reflective interview contest held after an AI seminar series at Yooshin Engineering. Participants had one-on-one conversations with an AI survey guide about their seminar experience — what stood out, what they tried with AI, how it went, and their honest feedback.

**Your task:** Read all the attached interview transcripts, pick **one winner** who will receive a Starbucks gift card, then output a **single self-contained HTML file** that acts as a dramatic winner-reveal ceremony.

**Evaluation criteria (internal only — do NOT reveal these anywhere in the output):**
- Depth and specificity of reflection (concrete stories beat vague impressions)
- Genuine engagement with the conversation (back-and-forth quality, not just short answers)
- Memorable moments — did something in the conversation make you pause, smile, or think?
- Honesty and vulnerability in feedback (both positive and constructive)
- Evidence of actually trying AI tools, not just talking about them abstractly

**Output format:**

Output a single, complete `<!DOCTYPE html>` file (HTML + CSS + JS, no external dependencies) that runs the following ceremony sequence when opened in a browser:

### Phase 1 — Drumroll (≈4 seconds)
- Dark background, spotlight-style radial gradient in the center
- A large "🥁 두구두구두구…" text pulses/shakes with increasing intensity
- A low-frequency CSS rumble animation on the whole page (subtle `translate` shake)
- A horizontal slot-machine strip rapidly cycles through **all participant names** (extracted from the transcripts — use `이름 (부서)` format) in a blur, like a spinning roulette — names should fly by vertically in the center, blurred, getting faster

### Phase 2 — Names slow down (≈3 seconds)
- The slot-machine strip decelerates with an easing curve — names become readable, then slow to a crawl
- The drumroll text fades out
- A brief suspenseful pause (0.5s) on the final name

### Phase 3 — Winner reveal (triggered after pause)
- The winner's name + department POPS in at massive scale (`6rem`+) with a spring/bounce keyframe animation — overshoot, settle
- Background EXPLODES: radial gradient burst from the center transitioning from dark to a warm gold/amber
- Hundreds of confetti particles rain down — use a JS confetti engine (pure JS, no library): small colored rectangles/circles with random rotation, horizontal drift, and gravity, spawned in bursts
- "🎉 축하합니다! 🎉" appears above the name with a typewriter or fade-in-up animation
- Starbucks gift card mention fades in below: "스타벅스 기프티콘이 전달될 예정입니다 ☕"
- Sparkle/star particles twinkle around the winner name using CSS `@keyframes` (small dots that scale up, glow, then fade)
- The whole winner card has a soft golden `box-shadow` glow that pulses

### Phase 4 — Thank-you footer (≈1s after reveal)
- A warm thank-you message fades in at the bottom in smaller text (Korean, 존대말):
  - Thanks everyone who participated
  - A brief, warm reason for the winner pick — do NOT reveal evaluation criteria; use something like "특히 생생하고 솔직한 이야기를 나눠주셨습니다" or "대화 속에서 진심이 느껴졌습니다"
- This text should feel understated next to the celebration above

### Technical requirements
- **One single `.html` file** — all CSS in `<style>`, all JS in `<script>`, zero external resources
- Works in modern Chrome/Edge/Safari — use standard CSS and JS only
- Responsive: looks good on both a projector (16:9 wide) and a phone screen
- All text in **Korean** (존대말)
- Use `requestAnimationFrame` for the confetti engine
- Use CSS `@keyframes` for all other animations (bounce, pulse, shake, fade, sparkle)
- Confetti should have at least 5 distinct bright colors, random sizes (4-10px), and last at least 5 seconds
- The slot-machine name cycling must include **every** participant name from the transcripts — hardcode them in a JS array
- Total runtime from page load to fully settled: ~10-12 seconds
- No user interaction required — everything auto-plays on load

**Important rules:**
- Do NOT list or rank participants anywhere visible
- Do NOT compare participants against each other
- Do NOT explain scoring methodology or criteria anywhere in the page
- The tone should feel like an over-the-top fun team celebration
