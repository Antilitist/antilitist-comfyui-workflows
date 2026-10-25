# Forger family autumn walk (regional) – Pony

![sample](sample.png)

Workflow: `forger_walk_pony.json`. Base: **Pony**. Strictly wholesome and family-friendly (Anya is a child): `rating_safe`, fully clothed, strong negatives.

## Files needed

| File | What | Download | Put it in |
|---|---|---|---|
| `ponyDiffusionV6XL_v6StartWithThisOne.safetensors` | Checkpoint: Pony Diffusion V6 XL by **PurpleSmartAI** | https://civitai.com/models/257749?modelVersionId=290640 | `ComfyUI/models/checkpoints/pony/` |
| `Anya_Forger_-_Spy_X_Family.safetensors` | LoRA: Anya Forger (Pony V1) by **ethensia** | https://civitai.com/models/919274?modelVersionId=1028945 | `ComfyUI/models/loras/spyxfamily/` |
| `Loid_Forger-75.safetensors` | LoRA: Loid Forger / Twilight (Pony v1.0) by **duongve13112002** | https://civitai.com/models/1296565?modelVersionId=1463314 | `ComfyUI/models/loras/spyxfamily/` |
| `SpyxFamilyYorXL-v1-07.safetensors` | LoRA: Yor Forger (Pony v1.0) by **turkey910** | https://civitai.com/models/159553?modelVersionId=477954 | `ComfyUI/models/loras/spyxfamily/` |

## Regional prompting (no custom nodes needed)

This workflow uses ComfyUI's **built-in** hook-LoRA and area nodes (core ComfyUI, https://github.com/comfyanonymous/ComfyUI):
`CreateHookLora` → `SetClipHooks` → `CLIPTextEncode` → `ConditioningSetAreaPercentage` per character, merged with `ConditioningCombine` on top of a whole-scene prompt. Each character's LoRA only affects its own region's prompt.

Install: update ComfyUI to a recent version (hook nodes were added in late 2024): run `update/update_comfyui.bat` (portable build) or `git pull` in your ComfyUI folder, then restart. Nothing else to install.

The JSON is in ComfyUI **API format**: drag it onto the canvas (or use Workflow → Open) and ComfyUI lays out the nodes for you. Set the KSampler seed to random.

## Regions and LoRA weights

Loid left (x 0–45%, y 15–100%, strength 0.75) LoRA 0.7; Anya center (x 30–70%, y 35–100%, strength 0.8) LoRA 0.62 (lower weight gives a cleaner face); Yor right (x 55–100%, y 15–100%, strength 0.75) LoRA 0.6; empty-sky region across the top 16% for bubbles. Negative includes `extra people, crowd, second child`. Overlapping regions with strength below 1 keep the three figures the same size. Hand-holding is in the prompt but rarely renders (the sample does not show joined hands). The bubbles in `sample_captioned.png` were added afterwards with Pillow (Comic Neue Bold).

## Trigger words

Anya: `anya forger, ahoge, meme` (+ `eden academy school uniform, gold trim, red ribbon` / `black dress`). Loid: `twilight` (+ `blonde hair, short hair, suit, red necktie`). Yor: `ChopioYor, black hair, red eyes, gold earrings` (+ modest outfit `outfit_1, office lady, collared shirt, white shirt, green vest, long sleeves`). Bond: no LoRA, `white fluffy dog, great pyrenees`.

## Settings

- Pass 1: euler_ancestral, normal, 28 steps, CFG 7, 1216x832, seed random
- Pass 2 (face/detail fix, built in): LatentUpscaleBy 1.5x -> KSampler 20 steps, CFG 6, denoise 0.42 -> final 1824x1248
- Tip: generate 6–10 seeds and pick; regional hook LoRAs make each image take about 2 minutes on a mid-range GPU.

## Credits

- **PurpleSmartAI**: https://civitai.com/models/257749?modelVersionId=290640
- **ethensia**: https://civitai.com/models/919274?modelVersionId=1028945
- **duongve13112002**: https://civitai.com/models/1296565?modelVersionId=1463314
- **turkey910**: https://civitai.com/models/159553?modelVersionId=477954

Questions or issues? Ask me on X: https://x.com/Antilitist
