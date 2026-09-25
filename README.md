# OTIBMFND: Optimal Transport and Information Bottleneck for Multimodal Fake News Detection

This is an official implementation for **OTIBMFND: OPTIMAL TRANSPORT AND INFORMATION BOTTLENECK FOR MULTIMODAL FAKE NEWS DETECTION**. If you like this repo, don't forget to give a star, and if possible cite this paper. Many thanks!

### Requirements
You can run `pip install -r requirements.txt` to deploy the environment.

### Directory Structure
```
|–– CNN_architectures/
|   |–– fp16_util.py
|   |–– lenet5_pytorch.py
|   |–– nn.py
|   |–– pytorch_efficientnet.py
|   |–– pytorch_inceptionet.py
|   |–– pytorch_resnet.py
|   |–– pytorch_vgg_implementation.py
|   |–– unet.py
|–– model/
|   |–– bert.py
|   |–– layers.py
|   |–– pivot.py
|   |–– pivot3.py
|–– pretrained_model/
|–– util/
|   |–– crop.py
|   |–– datasets.py
|   |–– lars.py
|   |–– lr_decay.py
|   |–– lr_sched.py
|   |–– misc.py
|   |–– pos_embed.py
|–– utils/
|–– data/
|   |–– train_clip_loader.pkl
|   |–– train_loader.pkl
|   |–– train_origin.csv
|   |–– ...
|–– Weibo_21/
|   |–– train_clip_loader.pkl
|   |–– train_loader.pkl
|   |–– train_datasets.xlsx
|   |–– ...
|–– clip_data_pre.py
|–– data_pre.py
|–– main.py
|–– models_mae.py
|–– run.py
|–– weibo21_clip_data_pre.py
|–– weibo21_data_pre.py
|–– clip_cn_vit-b-16.pt
|–– mae_pretrain_vit_base.pth
```

### Data Preparation
1. **Data Splitting**: In the experiments, we maintain the same data splitting scheme as the benchmarks.
2. **Weibo21 Dataset**: For the Weibo21 dataset, we follow the work from [(Ying et al., 2023)](https://github.com/yingqichao/fnd-bootstrap). You should send an email to Dr. [Qiong Nan](mailto:nanqiong19z@ict.ac.cn) to get the complete multimodal multi-domain dataset Weibo21.
3. **Weibo Dataset**: For the Weibo dataset, we adhere to the work from [(Wang et al., 2022)](https://github.com/yaqingwang/EANN-KDD18). In addition, we have incorporated domain labels into this dataset. You can download the final processed data from the link below. By using this data, you will bypass the data preparation step. Link: https://pan.baidu.com/s/1TGc-8RUt6BIHO1rjnzuPxQ code: qwer
4. **Data Storage**:
    - Place the processed Weibo data in the `./data` directory.
    - Place the Weibo21 data in the `./Weibo_21` directory.
5. **Data Preprocessing**: Run `clip_data_pre.py`, `data_pre.py`, `weibo21_data_pre.py`, and `weibo21_clip_data_pre.py` to preprocess the data of Weibo and Weibo21, respectively, in order to save time during the data loading phase.

### Pretrained Models
1. **Roberta**: You can download the pretrained Roberta model from [Roberta](https://drive.google.com/drive/folders/1y2k22iMG1i1f302NLf-bj7UEe9zwTwLR?usp=sharing) and move all files into the `./pretrained_model` directory.
2. **MAE**: Download the pretrained MAE model (`mae_pretrain_vit_base.pth`) from ["Masked Autoencoders: A PyTorch Implementation"](https://github.com/facebookresearch/mae) and move all files into the root directory.
3. **CLIP**: Download the pretrained CLIP model (`clip_cn_vit-b-16.pt`) from ["Chinese-CLIP"](https://github.com/OFA-Sys/Chinese-CLIP) and move all files into the root directory.

### Training
- **Start Training**: After processing the data and downloading the pretrained models, train the model by running:
  ```bash
  python main.py
  ```

### Citation / Reference
If you find this work useful in your research, please cite:
```bibtex
@article{zhu2027otibmfnd,
  title={OTIBMFND: OPTIMAL TRANSPORT AND INFORMATION BOTTLENECK FOR MULTIMODAL FAKE NEWS DETECTION},
  author={Anonymous Authors},
  journal={Under Review},
  year={2027}
}
