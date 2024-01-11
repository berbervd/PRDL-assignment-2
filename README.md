# Groepsopdracht Pattern Recognition & Deep Learning

## Important:
Link naar de overleaf:
https://www.overleaf.com/8233826145xpxxrhrqdhpf#cd651e 

Wat zit er in deze github:
- Jupyter notebook voor preprocessing
- Assignment description
- data zip file kan er niet bij >> moet je ff downloaden via de link op bb oid

## Data Description

### Data
- **Source**: Magnetic sensors on the scalp.
- **Units**: Tesla (xx* e-10).

### Data Files: `taskType_subjectID_number.h5`
- **Cross**:
  - Train (64 files): 16 rest, 16 motor, 16 math, 16 working memory (2 subjects?).
  - Test1 (16 files): 4 rest, 4 motor, 4 math, 4 working memory (2 subjects?).
  - Test2 (16 files): 4 rest, 4 motor, 4 math, 4 working memory (2 subjects?).
  - Test3 (16 files): 4 rest, 4 motor, 4 math, 4 working memory (2 subjects?).
- **Intra**:
  - Train (32 files): 8 rest, 8 motor, 8 math, 8 working memory (1 subject).
  - Test (8 files): 2 rest, 2 motor, 2 math, 2 working memory (1 subject).

### Data Structure
- **Shape of Each File**: 248x35624.
  - 248 rows (number of sensors).
  - 35624 columns (time steps of a recording).

### Data Format
- **File Extension**: H5 (hierarchical data format).
- **Format upon Reading**: Numpy array with shape 248x35624.

### Data Tasks
- Rest.
- Math & Story.
- Working Memory.
- Motor.

## Assignment
### Goal
- In brain decoding, there are two types of classification:
  - **Intra-Subject Classification**: Train and test models on the same subject(s).
  - **Cross-Subject Classification**: Train on one part of the data and test on a new, unseen part.

### Tasks
1. Choose a suitable deep learning model for the classification tasks and justify your choice.
2. Compare the accuracy of intra-subject and cross-subject classification using your model. Explain your results.
3. Explain the choices of hyper-parameters in your model architecture and analyze their influence on the results. How were they selected?
4. If there is a significant difference in training and testing accuracies, discuss possible reasons. Suggest alternative models or approaches to improve your results and justify your choice.

### Hints
- **Data Preprocessing**: Scaling of the data is necessary (min-max scaling, z-score normalization, or time-wise scaling/normalization).
- **Data Downsampling**: Every second corresponds to 2034 samples. Each file represents a duration of 17.5 seconds. Downsampling is advised to make DL processing faster.
- **Memory Management**: Use a loop, especially for the cross-subject part containing 64 files. Load small subsets of files in iterations for model fitting.


