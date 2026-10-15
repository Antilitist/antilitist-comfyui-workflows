# Anima + Smooth Detailer Booster (Megumin example)

![sample](sample.png)

Workflow: `anima_detailer.json` (drag into ComfyUI). Base: **Anima**. Keep prompts wholesome and SFW.

## Files needed

| File | What | Download | Put it in |
|---|---|---|---|
| `anima-base-v1.0.safetensors` | Diffusion model (Anima base) by **circlestone-labs** (Hugging Face) | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/diffusion_models/anima-base-v1.0.safetensors | `ComfyUI/models/diffusion_models/anima/` |
| `qwen_3_06b_base.safetensors` | Text encoder | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/text_encoders/qwen_3_06b_base.safetensors | `ComfyUI/models/text_encoders/anima/` |
| `qwen_image_vae.safetensors` | VAE | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/vae/qwen_image_vae.safetensors | `ComfyUI/models/vae/anima/` |
| `AEMegumin_ANIMA.safetensors` | LoRA: Megumin (Anima version; downloads as `AEMegumin.safetensors`, rename it) by **AEgirDelta** | https://civitai.com/models/549067?modelVersionId=3378977 | `ComfyUI/models/loras/megumin/` |
| `Smooth_Booster_Anima.safetensors` | LoRA: Smooth Detailer Booster (Anima Booster v2.0) by **DigitalPastel** | https://civitai.com/models/1145743?modelVersionId=3367283 | `ComfyUI/models/loras/anima/` |

The workflow expects the subfolders shown above (for example `anima\...` or `pony\...`). If you put files elsewhere, re-pick them in the loader nodes.

## Trigger words

Megumin triggers as above. The booster has no trigger; it helps to add `highly detailed, sharp focus, detailed background, intricate details`. Keep CFG 2–4.

## Settings

- Sampler euler, scheduler simple, 30 steps, CFG 4, ModelSamplingAuraFlow shift 3, 832x1216
- LoRA weights: Megumin 1.0 → Smooth Booster 0.5 (optional, chained; bypass the node or set it to 0 to disable)
- Seed: random

## Credits

- **circlestone-labs** (Hugging Face): https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/diffusion_models/anima-base-v1.0.safetensors
- Text encoder: https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/text_encoders/qwen_3_06b_base.safetensors
- VAE: https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/vae/qwen_image_vae.safetensors
- **AEgirDelta**: https://civitai.com/models/549067?modelVersionId=3378977
- **DigitalPastel**: https://civitai.com/models/1145743?modelVersionId=3367283

Questions or issues? Ask me on X: https://x.com/Antilitist
