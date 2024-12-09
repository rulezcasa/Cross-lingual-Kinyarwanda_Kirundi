
# Cross-lingual transfer of multilingual models on low resource African Languages

## Overview
Benchmarking cross-lingual transfer from Kinyarwanda to Kirundi using transformer(mBERT, AfriBERT, BantuBERTa) and traditional neural models (BiGRU, CNN, char-CNN). While monolingual models remain competitive, the analysis highlights the strong cross-lingual transfer capabilities in resource limited settings of transformer multilingual architectures. 







## Pre-print manuscript

https://arxiv.org/abs/2409.10965



## Directory structure

```
project_root/
├── requirements.txt
├── embeddings.ipynb
├── Transformer_Architectures/
│   ├── mBERT.ipynb
│   ├── AfriBERT.ipynb
│   └── BantuBERT.ipynb
│
├── Traditional_Architectures/
│   ├── BiGRU.ipynb
│   ├── CNN.ipynb
│   └── CharCNN.ipynb
│
└── Dataset_Cleaned/
    ├── zero_kin_train.csv
    ├── zero_kin_test.csv
    ├── zero_kir_train.csv
    └── zero_kir_test.csv
```




## Dataset

The dataset comprises of news articles from both languages Kinyarwanda and Kirundi labelled with the following classes sourced from [10.18653/v1/2020.coling-main.480](https://doi.org/10.18653/v1/2020.coling-main.480).

| Index | Category       |
|-------|----------------|
| 1     | Politics       |
| 2     | Sport          |
| 3     | Economy        |
| 4     | Health         |
| 5     | Entertainment  |
| 6     | History        |
| 7     | Technology     |
| 8     | Tourism        |
| 9     | Culture        |
| 10    | Fashion       |
| 11    | Religion       |
| 12    | Environment    |
| 13    | Education      |
| 14    | Relationship   |

The corpus was subjected to cleaning and converting the numberical labels to zero based. The cleaned comma seperated value dataset can be found on under ```Dataset cleaned``` directory of this repository. 

## Results

(a) Performance before and after fine tuning

| Model       | Accuracy before FT | F1 before FT | Accuracy after FT | F1 after FT |
|-------------|--------------------|--------------|-------------------|-------------|
| mBERT       | 0.5872             | 0.5917       | 0.8462           | 0.8422      |
| Afri BERT   | 0.7421             | 0.7474       | **0.8830**       | **0.8787**  |
| Bantu BERT  | 0.7454             | 0.7375       | 0.8657           | 0.8606      |
| BiGRU       | 0.2404             | 0.2300       | **0.8332**       | **0.8790**  |
| CNN         | 0.2190             | 0.2320       | 0.5913           | 0.5732      |
| Char-CNN    | 0.1916             | 0.1621       | 0.4879           | 0.4764      |



(b) Forgetting before fine-tuning

| Model       | Accuracy | F1 Score |
|-------------|----------|----------|
| mBERT       | 0.7884   | 0.7747   |
| Afri BERT   | 0.8498   | 0.8447   |
| Bantu BERT  | 0.8601   | 0.8555   |
| BiGRU       | 0.8851   | 0.8434   |
| CNN         | 0.8740   | 0.8660   |
| Char-CNN    | 0.6930   | 0.6823   |

(c) Forgetting Post Fine-Tuning

| Model       | Accuracy | Forget % |
|-------------|----------|----------|
| mBERT       | 0.7645   | 3.03     |
| Afri BERT   | 0.8061   | 5.14     |
| Bantu BERT  | 0.2172   | 74.00    |
| BiGRU       | 0.2329   | 73.68    |
| CNN         | 0.2207   | 74.86    |
| Char-CNN    | 0.1968   | 71.50    |

## Citation
If you use our work please cite:
```bibtex
@misc{thangaraj2024crosslingualtransfermultilingualmodels,
      title={Cross-lingual transfer of multilingual models on low resource African Languages}, 
      author={Harish Thangaraj and Ananya Chenat and Jaskaran Singh Walia and Vukosi Marivate},
      year={2024},
      eprint={2409.10965},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2409.10965}, 
}
```

## Acknowledgements

**Funding:** JS. Walia A. Chenat and H. Thangaraj
contributed to this work while undertaking a remote collaboration with the Department of Computer Science, University of Pretoria with the Data
Science for Social Impact (DSFSI) laboratory with Professor Vukosi Marivate.

**Open Access:** For open access purposes, the authors have applied a Creative Commons Attribution (CC BY) licence to any Author Accepted
Manuscript version arising.

**Data Access Statement:** This study involves secondary analyses of the existing datasets, that are described and cited in the text.

