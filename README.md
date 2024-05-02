# Rob-ASD

This repository contains code for the paper titled "Is Audio Spoof Detection Robust to Laundering Attacks?". Seven state-of-the-art (SOTA) Audio Spoof Detection systems are evaluated against laundering attacks. These systems are, 
- CQCC-GMM (https://github.com/asvspoof-challenge/2021/tree/main/LA/Baseline-CQCC-GMM/python)
- LFCC-GMM (https://github.com/asvspoof-challenge/2021/tree/main/LA/Baseline-LFCC-GMM/python)
- LFCC-LCNN (https://github.com/asvspoof-challenge/2021/tree/main/LA/Baseline-LFCC-LCNN)
- OC-Softmax (https://github.com/hashim19/AIR-ASVspoof)
- RawNet2 (https://github.com/eurecom-asp/rawnet2-antispoofing)
- RawGAT-ST (https://github.com/eurecom-asp/RawGAT-ST-antispoofing)
- AASIST (https://github.com/clovaai/aasist)

## Folder Structure

The repository is structured as follows:

| Folder | Description                                       |
|--------|---------------------------------------------------|
|__Audio Spoof Detection Systems__|
| `/ASD_ML/` | Contains code for CQCC-GMM and LFCC-GMM systems|
| `/LFCC-LCNN/` | Contains code for LFCC-LCNN system|
| `/AIR-ASVspoof/` | Contains code for OC-Softmax system|
| `/RawNet2/` | Contains code for RawNet2 system|
| `/RawGAT-ST-antispoofing/` | Contains code for RawGAT system|
| `/aasist/` | Contains code for AASIST system|
|__Evaluation__|
| `/Score_Files/` | Contains protocol files and evaluated score files|

## Database
This repository used two databases
- ASVSpoof 2019 (This database can be downloaded from the [ASVSpoof website] (https://www.asvspoof.org/))
- ASVSpoof Laundered Database (This database can be downloaded from the [ISSFLab website] (https://issf.umd.umich.edu/downloads/data))

## Reproducing EERs Using Score Files
The folder Score_Files contains score files generated by running SOTA audio spoof detection systems on the ASVSpoof 2019 eval dataset and ASVSpoof Laundered Database. 

The command to reproduce the EER looks like this,
```
python3 evaluate_tDCF_asvspoof19.py --protocol_filename= 'protocol filename' --score_filename='score filename
```

For example, if you want to reproduce the results for LFCC-GMM in the presence of babble noise with SNR = 10db, run the following command,
```
python3 evaluate_tDCF_asvspoof19.py --protocol_filename=babble_10_10_5_protocol.txt --score_filename=scores-lfcc-gmm-512-babble-10-10-5-asvspoof19-LA-labels.txt --score_file_has_keys
```

## Installation

### ASD_ML
Go inside ASD_ML directory, create a virtual environment, activate virtual environment, and then install the required libraries
```
cd ASD_ML
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```








