# Low-Light Image Enhancement via FourierTMamba: A HybridFrequency-Spatial Approach
![visual_results](fig/visual.jpg)
> **Abstract:** Low-light image enhancement in digital imaging field is critical
for applications such as surveillance, mobile photography and autonomous driving. Currently available methods, no matter retinexbased or purely frequency-based methods, often fail to deal with
complex illumination dynamics, leading to artifacts and unnatural illuminance distribution. This paper has proposed a hybrid frequency spatial based approach named FourierTMamba, which harnesses
the strengths of Transformer, Mamba and Fourier Transform for visual details refinement and illuminance restoration. Specifically, it employs cascade strategy that integrates preliminary enhancement
based on retinex decomposition, as well as fine-grained enhancement through dual-domain hybrid structure. Comprehensive experiments on public benchmark paired and unpaired datasets have
demonstrated that the proposed FourierTMamba significantly outperforms state-of-the-art methods with relative lightweight computation burdens.



# Model structure
![model struct](fig/model.png)



## Results (FourierTMamba)
Performance results of the FourierTMamba trained on paired dataset
<summary><strong>LOL</strong> </summary>
<img src = "fig/LOL.png"> 

<summary><strong>ViLSRW</strong></summary>
<img src = "fig/LSRW.png"> 

Performance results of the FourierTMamba trained on paired dataset
<summary><strong>Visual Results</strong></summary>
<img src = "fig/unpaired.png"> 

## Installation
The project is built with Python 3.8, PyTorch 1.8.1. CUDA 10.2, cuDNN 7.6.5
~~~
pip install -r requirements.txt
~~~

## 2. Prepare Dataset
Download the following datasets:

LOL-v1 [Baidu Disk](https://pan.baidu.com/s/1ZAC9TWR-YeuLIkWs3L7z4g?pwd=cyh2) (code: `cyh2`), [Google Drive](https://drive.google.com/file/d/1L-kqSQyrmMueBh_ziWoPFhfsAh50h20H/view?usp=sharing)

LOL-v2 [Baidu Disk](https://pan.baidu.com/s/1X4HykuVL_1WyB3LWJJhBQg?pwd=cyh2) (code: `cyh2`), [Google Drive](https://drive.google.com/file/d/1Ou9EljYZW8o5dbDCf9R34FS8Pd8kEp2U/view?usp=sharing)

LSRW dataset [[Baiduyun (extracted code: wmrr)]](https://pan.baidu.com/s/1XHWQAS0ZNrnCyZ-bq7MKvA)

### Unpaired datasets 
Please refer to [[Project Page of RetinexNet]](https://daooshee.github.io/BMVC2018website/).

## How to train?
For example:trianing on LOL-v1 dataset
```
python3 basicsr/train.py --opt Options/FourierTMamba_LOL_v1.yml
```

## How to test?
```
python3 Enhancement/test_from_dataset.py --opt Options/FourierTMamba_LOL_v1.yml --weights pretrained_weights/LOL_v1.pth --dataset LOL_v1
