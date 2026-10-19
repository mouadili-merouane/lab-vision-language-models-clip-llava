# Vision-Language Models Lab: CLIP & LLaVA

This repository contains my practical work on two vision-language models:

- **CLIP** : image–text similarity, zero-shot classification, prompt engineering and text-to-image retrieval.
- **LLaVA**: visual question answering, visual hallucinations and a small multimodal image assistant.

The notebook was developed and run on **Kaggle** with a **GPU T4 x2**.
The notebook already contains all the code, the outputs and my answers to the questions, so you can read the results directly without running it again.
---
## Lab content

| Part | Exercise | Topic |
|---|---|---|
| Part I — Lab statement (CLIP) 
  | 1 | Installation and model loading |
| | 2 | Load an image |
| | 3 | Image/text similarity |
| | 4 | Zero-shot classification |
| | 5 | Evaluation on 12 labeled images |
| | 6 | Prompt engineering with CLIP |
| Part B — CLIP image retrieval | 7 | Build an image database (normalized embeddings) |
| | 8 | Text-to-image retrieval |
| Part C — LLaVA | 9 | Architecture |
| | 10 | Run LLaVA |
| | 11 | Visual question answering (5 images × 5 questions) |
| | 12 | Hallucination |
| Part D — CLIP vs LLaVA | 13 | Comparative experiment |
| Final mini-project | — | Multimodal image assistant + bonus (CLIP retrieval → LLaVA explanation) |

## Repository structure

```
 ─ LAB — Vision-Language Models: CLIP & LLaVA.ipynb      # The notebook with code, answers and analysis
├─ README.md
├── cat-image/
│   └── cat.jpg               # Image used in Exercises 2, 3, 4 and 6
├── images/                   # 12 labeled images used in Exercise 5 (evaluation)
│   ├── airplane1.jpg, airplane2.jpg
│   ├── bird1.jpg, bird2.jpg
│   ├── car1.jpg, car2.jpg
│   ├── cat1.jpg, cat2.jpg
│   ├── dog1.jpg, dog2.jpg
│   └── horse1.jpg, horse2.jpg
└── images-part2/             # 22 images used from Exercise 7 to the end
    └── (the 12 images above + football, ball, basketball, tennis,
         person, building, landscape and food images)
```


---


## How to run the notebook on Kaggle ( As mentionned , The notebook already contains all the code, the outputs and my answers to the questions, so you can read the results directly without running it again.)

### 1. Upload the image folders as datasets

On Kaggle, each folder must be uploaded as a **dataset**:

1. Go to **Datasets → New Dataset** (or **Upload → New Dataset** from the notebook).
2. Drag the content of one folder (for example `images-part2`) and give the dataset the same name.
3. Click **Create**.
4. Repeat for `cat-image` and `images`.

### 2. Import the notebook and add the datasets as input

1. Create a new notebook and choose **File → Import Notebook**, then select `clip_llava_lab.ipynb`.
2. In the right panel, click **Add Input** and add the three datasets.

### 3. Turn on the GPU and the Internet

In the right panel, open **Settings**:

- **Accelerator**: choose **GPU T4 x2**. LLaVA is too heavy for the CPU.
- **Internet**: turn it **on**. It's needed to install the libraries and download the models from Hugging Face.

Changing these settings restarts the session.

### 4. Check the image paths

Update these variables in the notebook if needed:

| Variable | Exercise | Folder |
|---|---|---|
| `IMAGE_PATH` | Exercise 2 | `cat-image/cat.jpg` |
| `BASE_PATH` | Exercise 5 | `images` |
| `IMAGE_DIR` | Exercise 7 and after | `images-part2` |

### 5. Run the cells in order

1. **Cell 1**: installs the libraries (`transformers`, `torch`, `pillow`, `matplotlib`, `pandas`).
2. **Cell 2**: imports the libraries, selects the device and loads CLIP. Check that it prints `Device: cuda`.
3. Then run the rest of the notebook **from top to bottom**. Each exercise uses variables from the previous ones.

