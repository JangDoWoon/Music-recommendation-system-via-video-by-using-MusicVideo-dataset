# Music-recommendation-system-via-video-by-using-MusicVideo-dataset
본 프로젝트는 모정훈 교수님의 연구지도를 받아 수행한 스마트미디어 연구센터 프로젝트입니다.
# Flowchart
![image](https://user-images.githubusercontent.com/67357059/128814701-93b15448-5c91-4abd-909c-918e4297d2b6.png)

Emotion을 예측하기 위해 pretrained CNN Model을 사용하여 Video와 Music의 Feature vector를 추출한 후 embedding space에서 거리를 구할 수 있는 모델을 고안함.
# Feature vector extraction
Video는 I3D모델을 이용해 6개의 emotion을 예측하는 모델을 만든 후 마지막 layer를 없앤 후 좀 더 low한 Feature vector를 추출함. Music data 역시 2DCNN 모델을 이용해 6개의 emotion을 예측하는 모델을 만든 후 마지막 layer를 제거함. Video와 Audio의 Emotion을 예측하는 모델은 본인의 다른 repository에 있음.
# Mapping Embedding space
Video와 Music에서 추출한 feature vector를 이용해 두 벡터의 거리를 구할 수 있는 Space에 mapping
## Contrastive loss
두 벡터사이의 Class가 같으면 1 다르면 0에 가깝게 만들어줌. 각 Class는 Video와 Music에 tag되어 있는 emotion임.

![image](https://user-images.githubusercontent.com/67357059/128815829-da620b04-77de-4452-a8a0-aeacfc616bdc.png)
# Evaluation
* Test set을 생성한 후 각 Video로부터 거리가 가장 가까운 music을 뽑음. 
* 그 후 Video의 emotion tag가 Music의 emotion tag와 동일한지 확인 (정확도 추정).
* 결과적으로 정확도는 0.58이 나옴.
## Confusion matrix
* Neutral에 대한 부분이 개선되었지만 아직 못 맞추는 부분이 많음 ( 중립적인 부분에 대해서는 실제 사람이 추측을 하더라도 맞추지 못하는 경우가 많을 것임)
* 또한 Fear와 Tension의 경우 폭력적인 장면, 잔인한 장면, 두려움에 떠는 장면 등이 많이 포함되어 잘 classify되기 힘듦.

![image](https://user-images.githubusercontent.com/67357059/128816298-1a16693a-3640-4fbf-b339-de56f1c430c1.png)

# Reference
Yagya Raj Pandeya (2020) Deep learning based late fusion of multimodal information for emotion classification of music video. Springer
Quo vadis, action recognition? A new model and the kinetics dataset.
Fan Y, Lu X, Li D, Liu Y (2016) Video-based emotion recognition using CNN-RNN and C3D hybridnetworks. International conference on multimodal interfaces. Tokyo, Japan
