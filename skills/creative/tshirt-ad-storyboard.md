# T-Shirt Ad Concept and Storyboard — TikTok Shop

## When to use

Use after product-media analysis to propose a 30-second vertical ad for a specific plain T-shirt. Follow the selected pipeline's proposal, script, and scene-planning directors and their human approval gates.

## Concept decision

1. Start with the verified shirt invariants and a one-sentence delivery promise. Preserve the approved form and color in every literal product shot; lighting and grading may add mood but must not change the colorway being sold.
2. Offer distinct concepts that can be made from the accepted footage and available local tools. For each, state the first-frame hook, shot sequence, spoken message, CTA, music approach, runtime, and missing assets. Do not claim fabric composition, durability, fit benefits, price, discount, or stock level without user-supplied evidence.
3. When both Remotion and HyperFrames are available, present both with brief-specific strengths and tradeoffs before locking `render_runtime`. Remotion suits caption-led editing and existing React scene types; HyperFrames suits kinetic type and HTML/GSAP product motion. FFmpeg suits straightforward cuts. Record the approved choice in `decision_log` under `render_runtime_selection`.
4. Decide `composition_mode` separately: templated for a quick repeatable Shop format; atelier for a one-off hero ad. Record it in `decision_log`.

## Storyboard contract

For every beat, record start/end time, purpose, source asset ID or requested asset, visible shirt view, framing/camera movement, on-screen copy, narration, audio cue, transition, and identity check. The total must be exactly 30 seconds on a 1080×1920 canvas. Use the TikTok safe zone in `skills/creative/short-form.md` for text and CTA.

An adaptable rhythm is: 0–2 seconds hook; 2–8 seconds silhouette and color; 8–20 seconds fit/detail or styling from verified views; 20–26 seconds payoff; 26–30 seconds product and TikTok Shop CTA. Change timing when the accepted footage calls for it. Put visual interest in frame one and make each shot do a different job.

Prefer an exact approved packshot for the final product view. The CTA can tell viewers to open the TikTok Shop product link, but exact shop name, price, promotion, and availability require supplied facts. If no product photo exists, present a generic graphic concept as such and wait for approval before production.

## Hand-off and review

Persist the chosen concept in `proposal_packet`, spoken copy in `script`, and timed beats in `scene_plan`; put shirt invariants and per-shot acceptance checks in top-level `scene_plan.metadata.commercial_product`. Before the asset stage, review that the storyboard uses only verified views, all claims are sourced, the CTA is readable, the music/voice plan is explicit, and every shot has a feasible local tool path.

| Check | Ready when |
|---|---|
| Identity | Every literal shot preserves approved fit, neckline, sleeves, hem, and color. |
| Story | The first frame has a hook; each later beat adds a distinct reason to keep watching. |
| Evidence | Every product or offer claim has a supplied source; missing facts remain placeholders. |
| Feasibility | The accepted assets and selected runtime can produce every storyboard beat. |

Common pitfalls: planning a back view from a front-only photo, grading one colorway into another, and putting the CTA under TikTok controls.
