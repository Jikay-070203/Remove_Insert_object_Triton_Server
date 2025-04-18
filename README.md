# 🧠 Remove & Insert Object in Image Pipeline

This project is designed to **remove objects** using a mask and **insert new elements** into the image conditioned on a reference image. It is built using **Diffusers**, **UNet**, and **Asymmetric AutoEncoder** for high-quality image inpainting.

---

## 📦 Installation

```bash
cd remove_insert_t_object
pip install -r requirements.txt
```

---

## 🚀 How It Works

### 🔧 Components:

- `AsymmetricAutoencoderKL`: Latent encoder/decoder for images.
- `UNet2DConditionModel`: Core denoising model.
- `DDIMScheduler`: Manages denoising steps.
- Optional: `CLIPImageProcessor`, `StableDiffusionSafetyChecker`

### 🔁 Pipeline Flow:

1. **Inputs**:

   - Original image
   - Binary mask (object to be removed)
   - Conditioning image (content to insert)
   - Encoder hidden states (e.g., from text encoder)

2. **Preprocessing**:

   - Resize, crop, and mask inputs.
   - Encode images to latent space.

3. **Denoising Diffusion**:

   - Add noise to latent vector.
   - UNet denoises over T steps.
   - Classifier-free guidance enhances quality.

4. **Decode Output**:
   - Latents decoded via VAE.
   - Image is returned in PIL format.

---

## 🔬 Run Demo

### For Insertion

```bash
jupyter notebook insert_demo.ipynb
```

### For Removal

```bash
jupyter notebook remove_demo.ipynb
```

### Launch UI

```bash
python -m app
```

---

## 📂 File Structure

- `insert_remove_pipeline.py`: Core pipeline implementation.
- `utils.py`: Preprocessing and helper functions.
- `app.py`: UI-based image editor.
- `notebooks/`: Jupyter demos for insertion/removal.

---

## 🧪 Sample Outputs

| Original                  | Masked                  | Condition                  | Output                  |
| ------------------------- | ----------------------- | -------------------------- | ----------------------- |
| ![](samples/original.png) | ![](samples/masked.png) | ![](samples/condition.png) | ![](samples/output.png) |

---

## 📄 License

[GNU AGPL v3.0](https://www.gnu.org/licenses/agpl-3.0.html)  
Copyright © 2024 [Hieu Pham](https://github.com/hieupham)

# Run

# Install cuda-toolkit

```bash
cd remove_insert_t_object
pip install -r requirements.txt
```

---

## How to use

### 1. For UI app

```bash
python -m app
```

---

### 2. Examples

For examples please reference two files: `insert_demo.ipynb` and `remove_demo.ipynb`

#### a. For Insert

```bash
insert_demo.ipynb
```

#### b. For Remove

```bash
remove_demo.ipynb
```

---

## License

[GNU AGPL v3.0](https://www.gnu.org/licenses/agpl-3.0.html)  
Copyright © 2024 [Hieu Pham](https://github.com/hieupham). All rights reserved.
