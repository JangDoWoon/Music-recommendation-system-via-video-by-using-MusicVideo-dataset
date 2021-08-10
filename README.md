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
두 벡터사이의 Class가 같으면 1 다르면 0에 가깝게 만들어줌.

![image](https://user-images.githubusercontent.com/67357059/128815829-da620b04-77de-4452-a8a0-aeacfc616bdc.png)
