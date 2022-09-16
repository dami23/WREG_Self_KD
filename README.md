Code (pytorch) for ['Weakly Supervised Referring Expression Grounding via Target-Guided Knowledge Distillation']. This paper has been submitted to ICRA 2023.

### Preliminary
1. Please refer to MattNet(https://github.com/lichengunc/MAttNet) to install mask-faster-rcnn, REFER and refer-parser2. Follow Step 1 & 2 in Training to prepare the data and features.

2. Please follow the step in DTWREG (https://github.com/insomnia94/DTWREG) to acquire the parsed discriminative triads.

The experiments are conducted on one GPU (NVIDIA RTX 3090ti).

- python == 3.7.13
- pytorch == 1.10

### Training and evaluation
1. train the teacher model
CUDA_VISIBLE_DEVICES={GPU_ID} python ./tools/train_teacher.py --dataset {DATASET} --splitBy {SPLITBY} --exp_id {EXP_ID}

2. train the student model
CUDA_VISIBLE_DEVICES={GPU_ID} python ./tools/train_student.py --dataset {DATASET} --splitBy {SPLITBY} --exp_id {EXP_ID}

3. evaluate the model, and the acquired results with different settings are listed in output/easy_results.txt
CUDA_VISIBLE_DEVICES={GPU_ID} python ./tools/eval.py --dataset {DATASET} --splitBy {SPLITBY} --split {SPLIT} --id {EXP_ID}

{DATASET} = refcoco, refcoco+, refcocog. {SPLITBY} = unc for refcoco and refcoco+, google for refcocog.

### Pretrained Models
All pre-trained models and related data can be downloaded here.

### Acknowledgement
The code is based on DTWREG (https://github.com/insomnia94/DTWREG).