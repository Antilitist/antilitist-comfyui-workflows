# Halloween Mummy Megumin (KonoSuba) – Anima

![sample](sample.png)

Workflow: `halloween_mummy_megumin_anima.json` (drag into ComfyUI). Base: **Anima**. A cute, fully covered Halloween mummy costume over her usual outfit, witch hat on top, with a pumpkin bucket, a tiny ghost and bats on a dark background. Keep prompts wholesome and SFW.

## Files needed

| File | What | Download | Put it in |
|---|---|---|---|
| `anima-base-v1.0.safetensors` | Diffusion model (Anima base) by **circlestone-labs** (Hugging Face) | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/diffusion_models/anima-base-v1.0.safetensors | `ComfyUI/models/diffusion_models/anima/` |
| `qwen_3_06b_base.safetensors` | Text encoder | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/text_encoders/qwen_3_06b_base.safetensors | `ComfyUI/models/text_encoders/anima/` |
| `qwen_image_vae.safetensors` | VAE | https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/vae/qwen_image_vae.safetensors | `ComfyUI/models/vae/anima/` |
| `AEMegumin_ANIMA.safetensors` | LoRA: Megumin (Anima version; downloads as `AEMegumin.safetensors`, rename it) by **AEgirDelta** | https://civitai.com/models/549067?modelVersionId=3378977 | `ComfyUI/models/loras/megumin/` |

The workflow expects the subfolders shown above (for example `anima\...`). If you put files elsewhere, re-pick them in the loader nodes.

## Trigger words

`AEMegumindef, red eyes, brown hair, short hair, witch hat` (+ `1girl, solo, megumin`). Costume words that worked: `cute halloween mummy costume, loose bandage wraps over her black cape and red dress, long sleeves, fully covered, witch hat on top of the bandages`.

## Settings

- Sampler euler, scheduler simple, 30 steps, CFG 4, ModelSamplingAuraFlow shift 3, 832x1216
- Then 1.5x lanczos upscale + fix pass: 20 steps, CFG 4, denoise 0.3 (tiled VAE encode/decode), final 1248x1824
- LoRA weights: Megumin 1.0
- Seed: random (both samplers set to randomize)

## Credits

- **circlestone-labs** (Hugging Face): https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/diffusion_models/anima-base-v1.0.safetensors
- Text encoder: https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/text_encoders/qwen_3_06b_base.safetensors
- VAE: https://huggingface.co/circlestone-labs/Anima/resolve/main/split_files/vae/qwen_image_vae.safetensors
- **AEgirDelta**: https://civitai.com/models/549067?modelVersionId=3378977

Questions or issues? Ask me on X: https://x.com/Antilitist
