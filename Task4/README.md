Task 4 — Fine-tuning Stable Diffusion v1.5 with LoRA
1)Objective
This project fine-tunes the Stable Diffusion v1.5 model using LoRA (Low-Rank Adaptation) on the `lambdalabs/pokemon-blip-captions` dataset from Hugging Face. The goal is to teach the model to generate Pokémon-style images with higher fidelity to the dataset's art style.

---

2) Dataset
- **Source:** [lambdalabs/pokemon-blip-captions](https://huggingface.co/datasets/lambdalabs/pokemon-blip-captions)
- Contains ~833 Pokémon images with BLIP-generated text captions.
- Loaded automatically from Hugging Face `datasets` library — no manual download required.

---

3)Features
- **Pretrained Base:** `runwayml/stable-diffusion-v1-5`
- **LoRA Injection:** Applied to all attention layers in the UNet.
- **Training Framework:** [Hugging Face Diffusers](https://github.com/huggingface/diffusers)
- **Lightweight:** Only LoRA parameters are trained, base model stays frozen.
- **Outputs:** LoRA checkpoints + generated samples.

---

4)Installation
1. Create Virtual Environment (Recommended)
```bash
python -m venv sd_lora_env
source sd_lora_env/bin/activate   
2. Install Dependencies

pip install --upgrade pip
pip install -r requirements.txt
Training
5)Run:

python train_lora.py
