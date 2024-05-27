# Retinal OCT (Optical Coherence Tomography) Image Classification
> Kaggle에 공개된 Retinal OCT image를 다양한 CNN architecture로 classification
<br/>

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
### 1. VGG16
#### (1) Loss and Accuracy
* **Train and Valdiation Accuracy**
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/a74c8785-4bb2-40a0-af4e-e82577740f1c" align="left" width="32%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/2e9d4368-bb26-4d47-b53a-7c2a9e65b732" align="left" width="32%">
</p>
<br/><br/><br/><br/><br/><br/><br/>

* **Train and Valdiation Loss**
<p align="left">  <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/7dd75bdf-26bc-4bf2-a87e-fe585cc4c910" align="left" width="32%"> <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/e23d58d6-abcc-4346-8f39-b4f660649232" align="left" width="32%">
</p>
<br/><br/><br/><br/><br/><br/>

#### (2) Sensitivity and Specificity
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/31648bcc-c91e-47d5-b5d6-cb261a725728 width="400" height="200"><br/>

#### (3) ROC Curve
##### 1) One vs. Rest multiclass
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/9e835a36-3e83-4a8a-b414-d29b70380c80 width="300" height="300"><br/>
##### 2) One vs. One
<p align="left">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/8525e45c-170a-4a68-a8e6-2e4a9f68364b" align="left" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/411a0338-3dae-40a2-a258-c5affaac34f8" align="left" width="20%">
 <img src="(https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/ffc2acb8-6c6c-4bce-b325-7deb67b5592e" align="left" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/17bc65ff-00e3-4287-b0af-ce9d77efec78" align="left" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/5f3775cf-0076-40ce-a9f0-365c3f0337a2" align="left" width="20%">
 <img src="https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/c035fd7a-fab2-4799-9f03-328d2ec13b7b" align="left" width="20%">
</p>
<br/><br/><br/><br/><br/><br/>

#### (4) Predictions
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/cb27f616-eb0d-43bf-b127-452303fe1733 width="300" height="300"><br/>

#### (5) Grad-CAM
##### 1) Grad-CAM by Layers
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/cd82184b-567d-47f8-8877-5f0f1f6593fe width="800" height="200"><br/>
##### 2) Grad-CAM + Guided-Backpropagation + Guided Grad-CAM
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/887f9843-8ebe-4083-878f-bfd81026f5bf width="800" height="200"><br/>
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/aa985d92-13b5-456b-9235-d554edadef0f width="800" height="200"><br/>

#### (6) Final Visualization: Input image + Probability + Grad-CAMs
<img src=https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/1d3d4398-7cad-4d8f-8e4d-c4eefe0f2df3 width="800" height="400"><br/><br/>
