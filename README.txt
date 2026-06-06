================================================================
README — Robust Quality Classification of Germinated Oil Palm Seeds
COMP3029 Computer Vision Coursework | Session 2025/2026
Student: Kan Kai Zheng | ID: 20613147
================================================================

================================================================
1. ENVIRONMENT REQUIREMENTS
================================================================
- Platform : Google Colab 
- CUDA     : 12.1
- GPU/CPU  : T4-GPU
- Key dependencies: torchvision, opencv-python, scikit-learn,
                    seaborn, pandas, tqdm, matplotlib, Pillow

All dependencies are pre-installed in the standard Google Colab 
environment. No manual installation is required.

================================================================
2. GOOGLE DRIVE SETUP
================================================================
This notebook interfaces directly with Google Drive to load 
datasets and save model checkpoints. 

Please ensure the coursework dataset is located in your Google 
Drive under a folder named exactly: Computer Vision

Required directory structure:
My Drive/
└── Computer Vision/
    ├── seedsegment/        # Batch-1: Training and Validation
    │   ├── train/          (Subfolders: GoodSeed, BadSeed)
    │   └── test/           (Subfolders: GoodSeed, BadSeed)
    ├── dataset/            # Raw Images for Distribution Shift
    │   ├── NormalRoomLighting/
    │   └── LightBox/
    ├── csv/                # Ground Truth Annotations
    │   ├── NormalRoomLight_annotation.csv
    │   └── LightBox_annotation.csv
    └── CW_Data/            # Output Directory (Created automatically)

================================================================
3. CONFIGURATION (MARKER INSTRUCTIONS)
================================================================
If the dataset is stored in a non-standard location, you must 
update the BASE_DIR variable in the "LECTURER CONFIGURATION BLOCK" 
(located in the first code cell of Step 0):

    BASE_DIR = '/content/drive/My Drive/Computer Vision'

NOTE: The path uses "My Drive" (with a space), which is the 
default Google Drive mount path in Colab. This is the ONLY line 
of code that requires modification.

================================================================
4. EXECUTION INSTRUCTIONS
================================================================
Step 1 — Open 20613147_CW.ipynb in Google Colab.
Step 2 — Ensure GPU runtime is enabled:
         (Runtime → Change runtime type → T4 GPU → Save)
Step 3 — Run Step 0 and mount Google Drive when prompted.
Step 4 — Select Runtime → Run All.

The notebook will automatically:
- Load and verify the dataset (Step 0)
- Train the baseline ResNet-18 (Step 1)
- Evaluate across all three domains (Step 2)
- Generate Grad-CAM forensic visualisations (Step 3)
- Formulate and document the hypothesis (Step 4)
- Train the improved model with checkpointing (Step 5)
- Produce the final comparative analysis and charts (Step 6)
- Present discussion and conclusion (Step 7)

================================================================
5. REPRODUCIBILITY & QUICK EVALUATION
================================================================
- Random seed (42) is set globally via set_seed(42).
- torch.backends.cudnn.deterministic = True
- torch.backends.cudnn.benchmark = False

MARKER SHORTCUT: To skip training (~25 epochs total), pre-trained 
weights are saved automatically to CW_Data/ during the first run:
  - resnet18_baseline.pth     (baseline model)
  - best_improved_model.pth   (improved model, Epoch 14)
Load these directly and run only Steps 2, 3, and 6 for evaluation.

Note: Minor numerical differences in the 4th decimal place may 
occur if Colab assigns a different GPU architecture (e.g., L4 
instead of T4), but macro-level metric trends remain identical.

================================================================
6. TECHNICAL & OPTIMISATION NOTES
================================================================
- Dynamic Bounding Box Extraction: Batch-2 and Batch-3 utilise a 
  custom DynamicSeedDataset class. This crops seeds on-the-fly 
  directly from high-res source images, mitigating RAM exhaustion.
- Validation-Aware Checkpointing: Step 5 evaluates against the 
  unaugmented Batch-1 validation set at every epoch and saves only 
  the minimum validation loss weights (Epoch 14).
- Multiprocessing Stability: num_workers=0 is enforced on all 
  DataLoaders to prevent known Colab background thread crashes.
- Dataset Verification: Step 0 includes a runtime verification 
  code cell that prints actual seed counts from the loaded data,
  confirming the dataset summary table figures.

================================================================
7. SUBMITTED FILES
================================================================
Zip file: CW_20613147_Kan_Kai_Zheng.zip

Contents:
- 20613147_CW.ipynb          — Main executable notebook (Google
                               Colab compatible, fully executable)
- 20613147_Report.pdf        — Technical report (LNCS format,
                               8 pages + references)
- README.txt                 — This file
