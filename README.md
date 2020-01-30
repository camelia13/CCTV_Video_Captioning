# CCTV_Video_Captioning
Video captioning project using deep learning models. 

## 프로젝트 활동 일지
----------------------------------------------
### 20.1.29
- ECO: Efficient Convolutional Network for Online Video Understanding
- (https://paperswithcode.com/paper/eco-efficient-convolutional-network-for)
- 저자 깃허브 주소 (https://github.com/mzolfaghari/ECO-efficient-video-understanding)
- 논문 1차 리딩 완료, 주요 개념 학습 중
- 깃허브 코드 실행을 해보려고 했으나 오류 발생
#### issue :
- 영상을 모델에 넣기 위해서는 통째로 넣는 것이 아니라 N개의 샘플로 나누어서 학습을 시켜야 함
- 영상을 프레임 단위로 나눌 수 있는 코드가 (https://github.com/yjxiong/temporal-segment-networks#extract-frames-and-optical-flow-images)에 있으나 make과정에서 'E: Unable to locate package libboost1.55-all-dev' 오류 발생
- 프레임 추출 대신 우선 본 코드를 다시 실행해보려고 했으나 pre-train 파일이 없어서 막힘.

----------------------------------------------
### 20.1.30

#### process :

- 위에서 언급한 ECO 논문을 기반으로 한 코드를 사용하여 프로젝트를 진행하려고 했음.
- 그러나, 코드 양이 상당히 방대하고 오류 사항이 너무 많아 우선 다른 코드를 찾아보기로 함
- 좀 더 쉽게 구현이 가능한 코드를 먼저 찾아보고 ECO paper에 있는 이론들을 적용해보려고 함.
- 새로 찾은 코드는 video-caption.pytorch(https://github.com/xiadingZ/video-caption.pytorch)로 좀 더 쉽게 구현이 가능해보임

#### issue : 

- 튜토리얼을 따라 데이터를 받고 코드를 진행하는 중에 영상 프레임 단위로 쪼갠 이미지들이 네트워크에 크기와 매칭되지 않는 오류가 발생함
RuntimeError: size mismatch, m1: [12000 x 2048], m2: [4096 x 512] at /opt/conda/conda-bld/pytorch_1579022034529/work/aten/src/THC/generic/THCTensorMathBlas.cu:290
- 해당 오류를 디버깅하기 위해 코드를 분석했으나 네트워크 layer에 대한 부분을 찾지 못함
- 이미지 파일을 확인 해보려고 했으나 npy로 되어있어 불러오는 방법을 찾는 중임.

----------------------------------------------

Reference
----------------------------------------------
|#|title|source|note|
|:----:|:-----|:-------|:------|
|1|[ECO: Efficient Convolutional Network for Online Video Understanding](https://github.com/mzolfaghari/ECO-efficient-video-understanding)|ECCV2018|핵심 이론 및 실행 코드 참고|
|2|[TSN-Pytorch](https://github.com/yjxiong/tsn-pytorch)||영상 데이터 프레임 단위 추출|
|3|[video-caption.pytorch](https://github.com/xiadingZ/video-caption.pytorch)||
