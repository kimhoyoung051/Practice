# Retinal OCT (Optical Coherence Tomography) Image Classification
> Kaggle에 공개된 Retinal OCT image를 다양한 CNN architecture로 classification
<br/>

## Data Description
* Data citation
  * Kermany, Daniel; Zhang, Kang; Goldbaum, Michael (2018), “Labeled Optical Coherence Tomography (OCT) and Chest X-Ray Images for Classification”, Mendeley Data, V2, doi: 10.17632/rscbjbr9sj.2
  * http://www.cell.com/cell/fulltext/S0092-8674(18)30154-5
* Retinal OCT(Optical Coherence Tomography): 비침습적인 방법으로 시신경 유두, 망막 및 각막을 포함한 안구의 구조를 파악하고 분석하는 검사 (출처: 서울아산병원)
* 본 데이터에는 4가지 category의 OCT 사진이 존재
<img src = https://github.com/kimhoyoung051/kaggle-retinal-oct-classification/assets/164658426/13c91272-ede6-4756-a126-a8d8919dde01 width = "400", height = "100"><br/>
  * CNV: Choroidal neovascularization. Arrow head가 neovascular membrane이고, arrow가 subretinal fluid.
  * DME: Diabetic macular edema. 화살표는 intra retinal fluid를 표시.
  * Drusen: Early AMD (Ager related macular degeneration)에서 발견됨.
  * Normal: Foveal contour가 잘 유지되고 fluid나 drusen 등이 관찰되지 않음.
* Dataset Distribution
  * Train - 37,206 CNV, 11,349 DME, 8,617 Drusen, 51,140 Normal
  * Validation - 8 CNV, 8 DME, 8 Drusen, 8 Normal
  * Test - 242 CNV, 242 DME, 242 Drusen, 242 Normal
<br/>

## CNN Classification
### 1. VGG16

