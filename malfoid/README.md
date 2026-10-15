# Malfoid (FemDraco) – Anima

![sample](sample.png)

Workflow: `malfoid_anima.json` (drag into ComfyUI). Base: **Anima**. Keep prompts wholesome and SFW.

## Files needed

| File | What | Download | Put it in |
|---|---|---|---|
| `anima-base-v1.0.safetensors` | Diffusion model (Anima base) by **circlestone-labs** (Hugging Face) | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/diffusion_models/anima-base-v1.0.safetensors | `ComfyUI/models/diffusion_models/anima/` |
| `qwen_3_06b_base.safetensors` | Text encoder | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/text_encoders/qwen_3_06b_base.safetensors | `ComfyUI/models/text_encoders/anima/` |
| `qwen_image_vae.safetensors` | VAE | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/vae/qwen_image_vae.safetensors | `ComfyUI/models/vae/anima/` |
| `femdraco_redteneri_ANIMA_v1.0B-000010.safetensors` | LoRA: Draco "Malfoid" Malfoy Genderswap (FemDraco), v1.0B Anima, by **Kaybe9797** | https://civitai.com/models/2967285?modelVersionId=3366782 | `ComfyUI/models/loras/malfoid/` |

The workflow expects the subfolders shown above (for example `anima\...` or `pony\...`). If you put files elsewhere, re-pick them in the loader nodes.

## Trigger words

`femdraco, 1girl, long hair, pale blonde hair, asymmetrical bangs, parted hair, hair intakes, pale skin, (ringed eyes:0.7), light-blue eyes OR green eyes, black hoop earrings, green nails`; outfit: `hogwarts school uniform, black robe, grey sweater, collared shirt, green necktie, black pleated skirt, pantyhose, black loafers`

## Settings

- Sampler euler, scheduler simple, 30 steps, CFG 4, ModelSamplingAuraFlow shift 3, 832x1216
- LoRA weights: FemDraco 0.8
- Seed: random

## Credits

- **circlestone-labs** (Hugging Face): https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/diffusion_models/anima-base-v1.0.safetensors
- Text encoder: https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/text_encoders/qwen_3_06b_base.safetensors
- VAE: https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/vae/qwen_image_vae.safetensors
- **Kaybe9797**: https://civitai.com/models/2967285?modelVersionId=3366782

Questions or issues? Ask me on X: https://x.com/Antilitist
