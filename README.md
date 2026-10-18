# FashionGeneration AI — AI-Powered T-Shirt Design Generation

FashionGeneration AI explores how computer vision, neural networks, image processing, and generative AI can be used to analyze T-shirt images and create new design variations.

The project includes implementations ranging from a custom CNN and associative memory to pretrained vision models and diffusion-based image generation. It also includes image segmentation, feature visualization, front-and-back product processing, and generation reports.

## Key Features

- **Image preprocessing:** Standardize T-shirt images for consistent processing.
- **Background segmentation:** Extract garment masks using U²-Net through `rembg`.
- **Visual feature extraction:** Analyze images using CNN-based representations.
- **Colour analysis:** Extract colour-histogram features from product images.
- **Associative memory:** Implement Bidirectional Associative Memory (BAM) for pattern association and recall.
- **AI-based design generation:** Generate T-shirt variations using pretrained diffusion models.
- **Image-to-image transformation:** Explore alternative design mockups using Stable Diffusion pipelines.
- **Feature visualization:** Display CNN activation maps and visual regions of interest.
- **Front-and-back processing:** Generate design variations for different product views.
- **Audit and visualization:** Save generated images, compare results, and maintain processing records.

## Repository Structure

```text
FashionGeneration-AI/
├── ann_model.ipynb
├── baseline_model.ipynb
├── notebook.ipynb
├── notebook1.ipynb
├── notebook2.ipynb
├── notebook3.ipynb
├── tshirt_dataset/             # Local dataset; excluded from Git
├── results/          # Generated outputs; selected results only
├── requirements.txt
├── .gitignore
└── README.md
```

## Notebook Overview

### 1. `baseline_model.ipynb` — From-Scratch Baseline

Implements a basic image-processing and neural-network workflow without pretrained model weights.

- Image loading and preprocessing
- OpenCV-based foreground segmentation
- Custom CNN architecture
- Image augmentation
- CNN feature extraction and colour analysis
- BAM-based associative memory
- Algorithmic generation of geometric design patterns
- Output comparison and reporting

This implementation provides a baseline for studying the individual components. Its performance depends on the limited training data and the way the network is trained.

### 2. `ann_model.ipynb` — Neural Network and Design Generation

Implements a product-focused processing workflow for a T-shirt's front and back images.

- Product image loading and preprocessing
- Neural-network-based feature extraction
- Colour feature analysis
- Associative-memory processing
- Design variation generation
- Saving generated outputs and associated results

Refer to the notebook's individual cells for the exact model configuration and generation method.

### 3. `notebook.ipynb` — Image-to-Image Generation

Explores a pretrained vision and image-generation workflow.

- Pretrained ResNet18 feature extraction
- RGB colour-histogram analysis
- BAM-based feature association
- Image preprocessing and comparison
- Image-to-image generation using `stabilityai/sd-turbo`
- Generation and saving of multiple design variations

### 4. `notebook1.ipynb` — Segmentation and Inpainting

Extends the image-generation workflow with background segmentation and masked image editing.

- U²-Net background-mask extraction
- ResNet18 visual features
- Colour-histogram analysis
- BAM-based association and recall
- Stable Diffusion XL inpainting
- Generated-design visualization and comparison

### 5. `notebook2.ipynb` — Inpainting and Image-to-Image Experiments

Explores two diffusion-based generation approaches within the same notebook.

- GPU availability and device configuration
- Image preprocessing and segmentation
- ResNet18 feature extraction
- BAM-based analysis
- Stable Diffusion XL inpainting
- Stable Diffusion XL image-to-image generation
- Output visualization, saving, and memory cleanup

### 6. `notebook3.ipynb` — Multi-Product Processing Pipeline

Processes multiple T-shirt product sets, including front and back views.

- Loading product images and metadata
- U²-Net segmentation
- ResNet18 feature extraction and activation-map visualization
- Colour-histogram features
- BAM-based associative analysis
- Stable Diffusion XL inpainting
- Multiple design variations per product
- Front-and-back output comparison
- CSV audit reports and architecture visualizations

This notebook provides the broader multi-product workflow and records processing information for generated designs.

## Technology Stack

| Area | Technologies |
|---|---|
| Language | Python |
| Image processing | OpenCV, Pillow |
| Deep learning | PyTorch, Torchvision |
| Feature extraction | Custom CNN, ResNet18 |
| Background segmentation | U²-Net, rembg, ONNX Runtime |
| Associative memory | Bidirectional Associative Memory (BAM) |
| Image generation | Hugging Face Diffusers |
| Diffusion models | SD-Turbo, Stable Diffusion XL |
| Data handling | NumPy, Pandas |
| Visualization | Matplotlib |
| Development | Jupyter Notebook |

## Getting Started

### Prerequisites

- Python environment compatible with the installed dependencies
- Jupyter Notebook or JupyterLab
- Git
- Adequate RAM and disk space
- A compatible GPU for faster diffusion-based generation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/FashionMind-AI.git
cd FashionMind-AI
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Create a Virtual Environment

**Windows:**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS/Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

For GPU acceleration, install the PyTorch version compatible with your CUDA environment using the official [PyTorch installation guide](https://pytorch.org/get-started/locally/).

### 4. Prepare the Dataset

The product-processing notebooks expect images arranged as follows:

```text
tshirt_dataset/
└── selected/
    ├── set_1/
    │   ├── front.jpg
    │   └── back.jpg
    ├── set_2/
    │   ├── front.jpg
    │   └── back.jpg
    └── ...
```

Use the folder structure expected by the selected notebook. The single-product notebooks use their configured product paths, while `notebook3.ipynb` expects five product sets.

### 5. Run the Notebooks

Launch Jupyter:

```bash
jupyter notebook
```

Open the notebook you want to explore and execute its cells in order. Some notebooks download pretrained weights and require an internet connection on the first run.

## Output

Depending on the notebook, outputs may include:

- Processed product images and segmentation masks
- CNN feature representations and activation maps
- Colour-histogram features and BAM recall results
- Generated T-shirt design variations
- Image comparisons and architecture diagrams
- CSV files containing source-image and generation records

Output folders and filenames are configured within each notebook.

## Limitations

- The from-scratch baseline has limited training data and may not generalize well to unseen designs.
- Augmentation increases training variation but does not replace independent training images.
- BAM is an experimental associative-memory component; it does not directly control diffusion generation in every implementation.
- Generated images may alter garment details or introduce visual artefacts.
- Generation speed depends on hardware, model size, and inference settings.
- The notebooks use different processing configurations and should be evaluated independently.

## Future Development

- Expand the dataset with more T-shirt categories, styles, colours, and viewpoints.
- Evaluate the baseline and pretrained approaches using suitable quantitative metrics.
- Improve consistency between front and back design variations.
- Add user-controlled design options such as colour, print style, and pattern placement.
- Develop an interface for uploading reference images and reviewing generated results.
- Standardize dependencies and configuration across notebooks.

## License

A license can be added once the terms for using, modifying, and distributing the code have been selected.

---

**FashionGeneration AI** — Combining computer vision and generative AI to explore new possibilities in T-shirt design.
