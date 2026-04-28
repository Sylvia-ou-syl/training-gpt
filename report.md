# SEEM3650 Practical Exam Report

## Student Info
- Student ID: XYZ=259
- Due Date: May 4, midnight

---

## Step 2: Shakespeare Character-level Model

### Generated Shakespeare Samples (First 5 lines):
```
I by done what leave death,
And aproposely beef the are and sors blate though wat our fort
Thine the aftior than whating bods farse dowed
And nears and thou stand murs's consel.
```

---

## Step 3: Model Architecture Exploration

### Configuration (based on XYZ mod 4 = 259 mod 4 = 3)
- Remainder 3: Layers ∈ {2, 3, 5, 7}, Heads = 4 (fixed)
- Experiment: Fix number of heads at 4, vary number of layers

### Training Loss at Iteration 2000 for Different Layer Configurations

| Number of Layers | Validation Loss at iter 2000 |
|------------------|-------------------------------|
| 2                | 1.9011                        |
| 3                | 1.9235                        |
| 5                | 1.9167                        |
| 7                | 1.9036                        |

### Best Configuration
- **Best number of layers: 2**
- **Best number of heads: 4**
- **Lowest validation loss achieved: 1.9011**

The experiment shows that for this CPU-based BabyGPT model with limited training iterations, a smaller number of layers (2) with 4 attention heads achieved the best validation loss. This could be due to:
1. Smaller models can converge faster with limited training
2. Larger models (7 layers) may require more iterations to fully optimize
3. The block size of 64 characters may not fully leverage deeper architectures

---

## Step 4: Code Generation Model

### Dataset
- **Type**: Python code (since XYZ mod 2 = 259 mod 2 = 1)
- **Source**: Open-source Python code from GitHub repositories (Django, Flask, NumPy, pandas, scikit-learn, etc.)
- **Total characters**: 761,627
- **Training tokens**: 685,464
- **Validation tokens**: 76,163

### Generated Code Samples (First 20 lines):
```
    __:
    withml_core = np.cation("Buefwith ("-----") stable the (
               "stimport () import ost for mom the mas version.
     _cliest = Valing kead = "reobjection" = "sol_feature('pare)."


from mimport (shape in meargument(asamplese in of pads in commplocales_endenclay)


      X_trains.tout()
       weith_sout_ofile_content(time)

           c.restit[01]: 1, < anda_sstamples} = fiter jue(
                                "start",
        betcorum_aname_caluest_durray_linest,


---------------

import notaing arre escrimert
# If sencessimary array asstore sullts vale brom ur oblocalus in of defiguing mesetst.
```

### Favorite Generated Snippets:
The following snippets show interesting code-like structure with function definitions, imports, and class references:

```python
# Snippet 1: Shows function-like structure with parameters
Return assort {bename}_lightmorYAmer(andomation).astimatory====="bencon")
     f"{eacde_linest_dict"]:
             "def then_"Muldexeersort "deforkage linesion"
```

```python
# Snippet 2: Shows dictionary and function call patterns
X_tite= dist(n_N, + {shape_subelts)):
     mandom_splated(X] = time(test)
      tin classs.fit
```

```python
# Snippet 3: Shows import-like and parameter patterns
def _sort_str_to_devalue_his = ["keargomele"],
     "a IstimportHERTMansserIN_VECARCCSMR"EACERABortBaseErry",
       "Edection",
     "pai_name",
      "fuse_bach : "NoneAx(sclasssifiest_list_"
```

---

## Submission Checklist

### Step 2:
- [x] Shakespeare char samples saved in report.md (first 5 lines)

### Step 3:
- [x] Plots saved in `figures/`
- [x] Report validation loss and best settings in report.md

### Step 4:
- [x] data inside `data/code_generation/input.txt`
- [x] new configuration in `config/train_code_generation.py`
- [x] generated code samples in report.md

---

## Technical Notes

### Training Configuration Used (CPU):
- device: cpu
- compile: False
- eval_iters: 20
- block_size: 64
- batch_size: 12
- n_embd: 128
- max_iters: 2000
- dropout: 0.0

### Repository Structure:
```
nanoGPT/
├── data/
│   ├── shakespeare_char/      # Shakespeare dataset
│   └── code_generation/       # Python code dataset
├── config/
│   ├── train_shakespeare_char.py
│   └── train_code_generation.py
├── figures/
│   └── layers_vs_loss.png      # Architecture experiment plot
├── out-shakespeare-char/       # Shakespeare model checkpoints
├── out-code-generation/        # Code generation model checkpoints
├── out-layers-*/              # Experiment model checkpoints
├── report.md
├── train.py
└── sample.py
```
