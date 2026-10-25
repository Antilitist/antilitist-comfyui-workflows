# Halloween Mummy Frieren (Sousou no Frieren) – Illustrious

![sample](sample.png)

Workflow: `halloween_mummy_frieren_illustrious.json` (drag into ComfyUI). Base: **Illustrious-XL v2.0**. A cute, fully covered Halloween mummy costume with a pumpkin bucket, a tiny ghost and bats on a dark background. Keep prompts wholesome and SFW.

## Files needed

| File | What | Download | Put it in |
|---|---|---|---|
| `Illustrious-XL-v2.0.safetensors` | Checkpoint (Illustrious-XL v2.0, includes CLIP + VAE) by **OnomaAI Research** (Hugging Face) | https://huggingface.co/OnomaAIResearch/Illustrious-XL-v2.0/resolve/main/Illustrious-XL-v2.0.safetensors | `ComfyUI/models/checkpoints/illustrious/` |
| `frieren_littlejelly_ILL.safetensors` | LoRA: Frieren [4 outfits] Illustrious v1.0 by **LittleJelly** (downloads as `SousouNoFrieren_Frieren_IlluXL.safetensors`, rename it) | https://civitai.com/models/1187259?modelVersionId=1336431 | `ComfyUI/models/loras/frieren/` |

The workflow expects the subfolders shown above (for example `illustrious\...` or `frieren\...`). If you put files elsewhere, re-pick them in the loader nodes.

## Trigger words

`frieren, sousou no frieren, 1girl, solo, elf, pointy ears, grey hair, long hair, twintails, green eyes, parted bangs, earrings` (LoRA outfit tags: `FrierenCasual`, `FrierenWinter`, `FrierenDance`, `FrierenDress`). Keep `fern, purple hair, purple eyes` in the negative so you get Frieren, not Fern.

Costume words that worked: `cute halloween mummy costume, lots of white bandages wrapped around her arms, body and legs over a long-sleeved white sweater and long pants, bandage wrap on her head, loose bandage ends fluttering, boots, fully covered`.

## Settings

- Sampler euler_ancestral, scheduler normal, 42 steps, CFG 6, 832x1216
- Then 1.5x lanczos upscale + fix pass: 24 steps, CFG 6, denoise 0.3 (tiled VAE encode/decode), final 1248x1824
- LoRA weights: Frieren 0.85 (model and clip)
- Seed: random (both samplers set to randomize)

## Credits

- **OnomaAI Research** (Hugging Face): https://huggingface.co/OnomaAIResearch/Illustrious-XL-v2.0
- **LittleJelly**: https://civitai.com/models/1187259?modelVersionId=1336431

Questions or issues? Ask me on X: https://x.com/Antilitist
