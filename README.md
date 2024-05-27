# Retinal OCT (Optical Coherence Tomography) Image Classification
> Kaggle에 공개된 Retinal OCT image를 다양한 CNN architecture로 classification
<br/>

## Table of Contents
- **[Data Description](#Data-Description)**
- **[CNN Classification](#CNN-Classification)**
  * **[VGG16](#VGG16)**
  * **[ResNet50](#ResNet50)**
  * **[DenseNet121](#DenseNet121)**
<br/><br/>

## Data Description
* Data citation
  * Kermany, Daniel; Zhang, Kang; Goldbaum, Michael (2018), “Labeled Optical Coherence Tomography (OCT) and Chest X-Ray Images for Classification”, Mendeley Data, V2, doi: 10.17632/rscbjbr9sj.2
  * http://www.cell.com/cell/fulltext/S0092-8674(18)30154-5
* Retinal OCT(Optical Coherence Tomography): 비침습적인 방법으로 시신경 유두, 망막 및 각막을 포함한 안구의 구조를 파악하고 분석하는 검사 (출처: 서울아산병원)
* 본 데이터에는 4가지 category의 OCT 사진이 존재<br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/13c91272-ede6-4756-a126-a8d8919dde01 width="800" height="200"><br/>
  * CNV: Choroidal neovascularization. Arrow head가 neovascular membrane이고, arrow가 subretinal fluid.
  * DME: Diabetic macular edema. 화살표는 intra retinal fluid를 표시.
  * Drusen: Early AMD (Ager related macular degeneration)에서 발견됨.
  * Normal: Foveal contour가 잘 유지되고 fluid나 drusen 등이 관찰되지 않음.
* Dataset Distribution
  * Train - 37,206 CNV, 11,349 DME, 8,617 Drusen, 51,140 Normal
  * Validation - 8 CNV, 8 DME, 8 Drusen, 8 Normal
  * Test - 242 CNV, 242 DME, 242 Drusen, 242 Normal
<br/><br/>

## CNN Classification
### VGG16
#### (1) Loss and Accuracy
* **Train and Valdiation Accuracy**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/a74c8785-4bb2-40a0-af4e-e82577740f1c" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/2e9d4368-bb26-4d47-b53a-7c2a9e65b732" width="32%">
</p>
<br/>

* **Train and Valdiation Loss**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/7dd75bdf-26bc-4bf2-a87e-fe585cc4c910" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/e23d58d6-abcc-4346-8f39-b4f660649232" width="32%">
</p>
<br/>

#### (2) Sensitivity and Specificity
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/31648bcc-c91e-47d5-b5d6-cb261a725728 width="400" height="200"><br/>

#### (3) ROC Curve
##### 1) One vs. Rest multiclass
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/9e835a36-3e83-4a8a-b414-d29b70380c80 width="300" height="300"><br/>
##### 2) One vs. One
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/8525e45c-170a-4a68-a8e6-2e4a9f68364b" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/411a0338-3dae-40a2-a258-c5affaac34f8" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ffc2acb8-6c6c-4bce-b325-7deb67b5592e" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/17bc65ff-00e3-4287-b0af-ce9d77efec78" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/5f3775cf-0076-40ce-a9f0-365c3f0337a2" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/c035fd7a-fab2-4799-9f03-328d2ec13b7b" width="15%">
</p>

#### (4) Predictions
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/cb27f616-eb0d-43bf-b127-452303fe1733 width="300" height="300"><br/>

#### (5) Grad-CAM
##### 1) Grad-CAM by Layers
* Prediction: CNV <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/cd82184b-567d-47f8-8877-5f0f1f6593fe width="600" height="150"> <br/>
##### 2) Grad-CAM + Guided-Backpropagation + Guided Grad-CAM
* Prediction: CNV
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/887f9843-8ebe-4083-878f-bfd81026f5bf width="800" height="200">
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/aa985d92-13b5-456b-9235-d554edadef0f width="800" height="200" <br/>

#### (6) Final Visualization: Input image + Probability + Grad-CAMs
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/1d3d4398-7cad-4d8f-8e4d-c4eefe0f2df3 width="800" height="400"> <br/><br/><br/>

### ResNet50
#### (1) Loss and Accuracy
* **Train and Valdiation Accuracy**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/6084a454-6aeb-4172-bb7f-cb8e08d5776d" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/d0a716ab-c8ce-4b10-a9d5-b10ac638dd20" width="32%">
</p>
<br/>

* **Train and Valdiation Loss**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/d32e4f62-885d-498c-b438-5e41d2ffe422" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/bb5cd4d1-8102-441d-97e5-72625db8fec7" width="32%">
</p>
<br/>

#### (2) Sensitivity and Specificity
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/482d9c48-4517-4d5d-bb19-b39a015762c5 width="400" height="200"><br/>

#### (3) ROC Curve
##### 1) One vs. Rest multiclass
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/c6d5b368-9a7b-494e-bd03-c54449ce8432 width="300" height="300"><br/>
##### 2) One vs. One
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/bde8fc17-cfcc-4159-8e9c-a552f9416556" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/f9b48609-e297-4731-9f68-650c6ab65dfa" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/a7593a14-035f-43e2-bd2c-4fa4885a509f" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/fbb5a296-1464-47db-9e91-0d5deff9e32a" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/7e89e29c-a4bb-4324-b160-60c3f5926c54" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/fcd421df-fa3b-4d24-8139-bdf097d165ff" width="15%">
</p>
<br/>

#### (4) Predictions
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/45f3249a-363c-453b-92e6-5ebdd1c9f15c width="300" height="300"><br/>

#### (5) Grad-CAM
##### 1) Grad-CAM by Layers
* Prediction: Normal <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/76483001-5c9d-4b36-9c9d-b6b1eff3d3c9 width="600" height="150"> <br/>
* Prediction: CNV <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/7cbe9243-98f1-4e5a-8c26-480544f52788 width="600" height="150"> <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/77c80ae2-a92f-4b3c-a131-ba4f67bafc61 width="600" height="150"> <br/>
* Prediction: Drusen <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/e4764c48-d56d-4187-aaad-00dca493f6dc width="600" height="150"> <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/9eca0f4d-2c19-437d-9991-8edc7528c0aa width="600" height="150"> <br/>
* Prediction: DME <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/66150da8-fe31-430e-8eb8-1755306e339d width="600" height="150"> <br/>
##### 2) Grad-CAM + Guided-Backpropagation + Guided Grad-CAM
* Prediction: Drusen <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/e9b48f99-d0a4-4ea6-86d2-89443b58db8c width="800" height="200"> <br/>
* Prediction: CNV <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/27bd439d-bf16-448a-8b17-ee92d92a631e width="800" height="200"> <br/>

#### (6) Final Visualization: Input image + Probability + Grad-CAMs
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/da90916e-5c34-4f16-9397-81840e63f0d0" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/47bfafc8-0660-4673-969a-580d810a2b30" width="20%">
  <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/283d26d2-a9aa-45d8-b875-b0bfb8b5479b" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/e2dc62f4-7f76-4e69-8621-f39f97830f3b" width="20%">
</p> <br/>
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/bf592ac8-7721-4f5e-a652-18760a2d6bd3" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/c927a1aa-b870-45f9-992d-8a363caae133" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/202407df-9240-4a6d-a17c-e3569e6dfd11" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/283d26d2-a9aa-45d8-b875-b0bfb8b5479b" width="20%">
</p> <br/><br/><br/><br/>


### DenseNet121
#### (1) Loss and Accuracy
* **Train and Valdiation Accuracy**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/8c169e87-935d-4db7-90f4-4bd417bfcffb" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/1f2883aa-9601-423a-b8ad-349a1f52c4b0" width="32%">
</p>
<br/>

* **Train and Valdiation Loss**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ed6570c9-1890-42f5-b30c-12e98a9b9e2e" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/8b9acc29-6d93-48c5-9cc9-0b57dbbc8f2a" width="32%">
</p>
<br/>

#### (2) Sensitivity and Specificity
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ba6defc3-3f39-4324-821d-a519cab05bfe width="400" height="200"><br/>

#### (3) ROC Curve
##### 1) One vs. Rest multiclass
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/4638eeb8-7a08-40e7-9423-e1f7f441b7a5 width="300" height="300"><br/>
##### 2) One vs. One
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/702bada9-98a2-4543-bcb6-4821c26bfe37" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/95ff21f5-3d1c-49c5-ac1b-43477625724a" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/d5601c12-6179-4dcf-90cc-105ed935de70" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/0c0abf06-da42-4093-80b6-190554e53076" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/3db9656a-52e3-45e6-836b-b68cddabb8de" width="15%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/90a4d09e-c184-4a4c-a46b-fcfc400edbb8" width="15%">
</p>
<br/>

#### (4) Predictions
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/9fce3871-89e3-49c8-acf3-8413b15d1500 width="300" height="300"><br/>

#### (5) Grad-CAM
##### 1) Grad-CAM by Layers
* Prediction: CNV <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/620179a2-52c2-4b3c-ba7c-d83c54644cfd width="600" height="150"> <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ae352457-0faa-4a78-9bb8-838df93e5c3f width="600" height="150"> <br/>
* Prediction: Drusen <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/13e14ddd-cbc6-4063-8aa7-db5f7e91d7dd width="600" height="150"> <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/4e8b5798-7f0e-4e93-bd07-428d6cff086d width="600" height="150"> <br/>
* Prediction: DME <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/1a4861f4-7a46-40f1-9f92-45d484970703 width="600" height="150"> <br/>
##### 2) Grad-CAM + Guided-Backpropagation + Guided Grad-CAM
* Prediction: Normal <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/21aa106e-49d9-40f2-a8b9-a9b2419ed921 width="800" height="200"> <br/>
* Prediction: CNV <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ca8c47b0-7fdb-4e91-b3af-b7181a396fa5 width="800" height="200"> <br/>
* Prediction: Drusen <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/af70a8c5-c2a6-4c0e-838a-19bbf4df78d1 width="800" height="200"> <br/>
* Prediction: DME <br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/24c15ce2-b8f0-4c17-b68e-698fc004882e width="800" height="200"> <br/>

#### (6) Final Visualization: Input image + Probability + Grad-CAMs
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/e6e9164c-29df-4d3c-a2a6-5e3039a9d03f" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/28730ac4-5f4a-4a9d-b785-670862809701" width="20%">
  <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/266e59b1-51c7-4cff-beb6-4fdf6a40499c" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/b533a605-04d6-43e7-bdb5-48e3e1a1fde3" width="20%">
</p> <br/>
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/6aced307-e172-447a-b0a8-0e25179064ec" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/adb40624-c422-49fc-88f2-6bedad838e18" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/bdca33f9-d840-4eca-943c-f8e6c82f6ad3" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ed09f386-450c-4512-bbdf-34fc44553c72" width="20%">
</p> <br/><br/><br/><br/>
