# TikTok Shop Ad Finishing — Local Edit and Export

## When to use

Use after approval of the product storyboard and assets to finish a 30-second 9:16 ad with local tools. Follow the selected pipeline's asset, edit, and compose directors; this skill adds apparel fidelity and VoiceStudio hand-off checks.

## Edit and audio

1. Build from accepted source clips and approved graphics only. Record exact in/out points, crop, overlays, narration, music, and subtitles in `edit_decisions`; keep source paths and license/provenance in `asset_manifest`.
2. For the requested **VoiceStudio local** voice, discover its actual local app/CLI/export route before use. Export narration as a WAV or other local file under `projects/<project-id>/assets/audio/`, then verify duration, sample rate, intelligibility, and that no cloud synthesis was invoked. If the route cannot be verified, surface a blocker and ask before using another voice provider or dropping narration. Do not pretend `tts_selector` is VoiceStudio.
3. Use a user-supplied, licensed local music file in `music_library/` or `projects/<project-id>/assets/music/`. If none exists, ask the user to choose a track or approve a no-music treatment. Use `audio_mixer` for voice/music balance and check the final mix for clipping.
4. Use `subtitle_gen` for timed captions and `remotion_caption_burn` when Remotion was approved for word-level captions. Keep captions within the safe zone, high contrast, and consistent with the actual spoken words. Do not silently switch render runtime to obtain a caption effect.
5. Compose with the approved `video_compose` runtime, then use local FFmpeg/ffprobe-based verification. Write all outputs under the project workspace.

## Export contract

Use the `tiktok` profile in `lib/media_profiles.py`: MP4, 1080×1920, 30 fps, H.264 video, AAC audio. Target exactly 30 seconds unless a documented edit decision approves a small delivery tolerance. Place essential copy inside the 900×1400 centered safe zone from `skills/creative/short-form.md`; leave TikTok UI space clear.

## Final review

Inspect the first frame, every shot join, detail/fit moments, caption peaks, and final packshot at phone size. Compare the shirt against approved references after crop, grade, overlays, and compression. Confirm color and silhouette, accurate claims, audible voice, music rights, caption timing, CTA legibility, file duration, resolution, codecs, and that the MP4 opens. Record findings and paths in `render_report`. A wrong color/form or unverified voice route blocks delivery; fix the smallest failing part and review again within the pipeline's revision limits.

| Check | Ready when |
|---|---|
| Product | The exported video still matches the approved shirt references. |
| Sound | The approved VoiceStudio file and licensed music are present and balanced. |
| Captions and CTA | Spoken words match captions; the Shop action is legible in the safe zone. |
| File | `ffprobe` confirms 1080×1920, 30 fps, H.264/AAC, and the approved duration. |

Common pitfalls: treating installed VoiceStudio app data as a working export interface, using an unlicensed trend track, and checking only the preview instead of the exported MP4.
