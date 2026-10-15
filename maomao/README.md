# Maomao (The Apothecary Diaries) – Pony

![sample](sample.png)

Workflow: `maomao_pony.json` (drag into ComfyUI). Base: **Pony**. Keep prompts wholesome and SFW.

## Files needed

| File | What | Download | Put it in |
|---|---|---|---|
| `ponyDiffusionV6XL_v6StartWithThisOne.safetensors` | Checkpoint (Pony Diffusion V6 XL, includes CLIP + VAE) by **PurpleSmartAI** | https://civitai.com/models/257749?modelVersionId=290640 | `ComfyUI/models/checkpoints/pony/` |
| `maomao_320544_PONY_v1.safetensors` | LoRA: Maomao (7+ Outfits) [Pony XL] v1 by **dude_** (Civitai file name differs; rename to match the workflow or re-pick it in the LoRA node) | https://civitai.com/models/320544?modelVersionId=359425 | `ComfyUI/models/loras/maomao/` |

The workflow expects the subfolders shown above (for example `anima\...` or `pony\...`). If you put files elsewhere, re-pick them in the loader nodes.

## Trigger words

`maomao` (plus `green hair, blue eyes, blunt bangs, freckles, single hair bun`); start prompts with `score_9, score_8_up, score_7_up, source_anime, rating_safe`

## Settings

- Sampler euler_ancestral, scheduler normal, 25 steps, CFG 7, 832x1216
- LoRA weights: Maomao 0.9 (model and clip)
- Seed: random

## Credits

- **PurpleSmartAI**: https://civitai.com/models/257749?modelVersionId=290640
- **dude_** (Civitai file name differs; rename to match the workflow or re-pick it in the LoRA node): https://civitai.com/models/320544?modelVersionId=359425

Questions or issues? Ask me on X: https://x.com/Antilitist
