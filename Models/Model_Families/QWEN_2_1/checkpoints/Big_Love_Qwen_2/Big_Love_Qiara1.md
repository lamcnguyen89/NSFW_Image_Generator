Finetune of Qwen Image 2.1 for image editing and txt2img. Reproduces faces very reliably with very good anatomy. Tack sharp like the base model, trained on various NSFW concepts giving it a Western look.
For best quality render at least 2 megapixels (1184×1776) or even 4 megapixels (1664×2512). The workflow includes the custom sampler with official sigmas (extended for 6 & 10 steps) and a KSampler as an alternative. There is also a deactivated option to adjust softness/sharpness via a turbo LoRA ratio (−0.3 to 0.5) — download the turbo LoRA under Optional Files and place it in ComfyUI's lora folder. For more sharpness you can also use the er_sde sampler instead of Euler.
No training files are provided — train directly on the int8 or bf16 version with the turbo option of AI-Toolkit.

With 8+ GB VRAM I recommend the int8 version (if you have Triton installed in ComfyUI), because it works fastest on all GPUs and has the highest 8-bit precision. Otherwise use mxfp8 with 5xxx GPUs (if you have CUDA 13 installed) or fp8 mixed in all other cases.
With 4–6 GB VRAM best grab the nvfp4 version with a 5xxx GPU (if you have CUDA 13 installed), otherwise the int4 or GGUF version. To make the GGUF version work in ComfyUI, you need to add the ComfyUI-GGUF node.
With 16 GB VRAM you can also use the bf16 version, but needs twice the generation time of int8. Only if you need absolute precision.
