# CycleGAN - Image-to-Image Translation without Paired Data

This project implements a CycleGAN model using PyTorch for unpaired image-to-image translation. The model can learn to translate between two visual domains (e.g., horses ↔ zebras, summer ↔ winter) without requiring paired training examples.

## 📌 Features

- PyTorch implementation of the CycleGAN paper
- Unpaired image translation using cycle-consistency loss
- Residual blocks for improved image generation
- Support for multiple image domains
- Flexible training and testing pipelines

## 🧠 How it Works

CycleGAN uses two generators and two discriminators:

- `Generator A2B`: Translates images from domain A to domain B.
- `Generator B2A`: Translates images from domain B to domain A.
- `Discriminator A`: Distinguishes real A images from generated A-like images.
- `Discriminator B`: Distinguishes real B images from generated B-like images.

The key idea is **cycle consistency**:  
If you translate an image to another domain and then back again, you should recover the original image.

## 🖼️ Example Applications

- Horse ↔ Zebra
- Summer ↔ Winter
- Day ↔ Night
- Monet ↔ Photograph

## 🛠️ Installation

```bash
git clone https://github.com/yourusername/cyclegan-project.git
cd cyclegan-project
pip install -r requirements.txt
```

📂 Dataset

You can use unpaired datasets from CycleGAN Dataset (from Zhu et al.).

```bash
# Example: Download horse2zebra dataset
bash ./datasets/download_cyclegan_dataset.sh horse2zebra
```

🚀 Training

```bash
python train.py --dataroot ./datasets/horse2zebra --epochs 200 --batch_size 1 --lr 0.0002
```

Options:

--dataroot: Path to the dataset

--epochs: Number of training epochs

--batch_size: Training batch size

--lr: Learning rate

🧪 Testing

```bash
python test.py --dataroot ./datasets/horse2zebra --epoch 200
```

📈 Results

Results are saved in the results/ directory after testing. You will find input, fake, and reconstructed images for visual comparison.

Dataset Link;
```bash
https://www.kaggle.com/datasets/balraj98/summer2winter-yosemite
```
