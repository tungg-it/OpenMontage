# Product Media Analysis — TikTok Shop Apparel

## When to use

Use before planning an ad for a specific garment when the user may supply a reference video, product photos, or recorded footage. This skill supplements the selected pipeline's research/idea and scene-planning directors; it does not replace their artifacts or approval gates.

## Inputs and routing

- Inventory each supplied file and its source, rights, resolution, duration, frame rate, orientation, and audio. Keep product identity references separate from mood or editing references.
- If a video is **inspiration**, first follow `skills/meta/video-reference-analyst.md`. If it is **footage to edit**, use the pipeline's source-media review and the local `video_analyzer`, `scene_detect`, `frame_sampler`, and `audio_probe` tools as available in the registry.
- Inspect photos at full resolution. Record front/back view, collar, sleeves, hem, fit, fabric texture, print/logo absence or placement, and the actual color under neutral light. A reference video's shirt is not evidence of the offered SKU.
- If no actual SKU image or footage exists, mark product depiction as **unverified**. A generic shirt illustration may be proposed only as a clearly labeled concept; do not present it as the actual TikTok Shop item.

## Analysis

1. Make a source inventory with file path, provenance, role (`product_identity`, `usable_footage`, `style_reference`, `audio`), technical quality, and rights status. Do not invent missing files.
2. For video, identify candidate in/out points and inspect the opening, movement peaks, transitions, and closing frame. Note whether the shirt remains visible, sharp, correctly colored, and suitable for a 9:16 crop.
3. Write a **keep / trim / reject / create** table for every candidate shot. Give the reason and the exact missing material for any proposed new shot. Prefer usable real footage for fit, drape, texture, and model interaction.
4. Define product invariants from approved sources: silhouette and fit, neckline, sleeve length, hem, colorway, fabric/print details, and any exact shop artwork. Distinguish known facts from visual assumptions.
5. Hand the source inventory and shot decisions to the selected pipeline's canonical `research_brief` or `brief`, then carry accepted source IDs and product invariants into `scene_plan.metadata.commercial_product` and `asset_manifest` as described in `skills/creative/commercial-product-video.md`.

## Acceptance check

| Check | Ready when |
|---|---|
| Product fidelity | Every literal shirt shot has an approved identity source and a feasible camera/crop. |
| Editorial selection | Each kept shot has a role, usable time range, and reason to survive the 30-second cut. |
| Missing coverage | Proposed new shots name the required view or action; no unseen back, fit, or material property is invented. |
| Provenance | File paths and rights are traceable in the downstream artifacts. |

Stop product-specific generation when identity references are insufficient; present the missing input or an explicitly generic treatment for approval.
