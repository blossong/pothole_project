# 딥러닝을 활용한 도로 포트홀 분류 및 탐지모델

## 프로젝트 개요
- 최근 여름철 폭우 또는 겨울철 폭설로 인한 도로 노면 이상 다수 발생
- 특히 도로 위 구멍, 포트홀에 의한 타이어 손상 및 급작스러운 조향에 따른 사고 위험
- **프로젝트 목표 : 이미지나 영상의 도로에서 포트홀을 감지하는 분류 모델, 탐지 모델 생성**
- 분류모델 : 정상 노면 상태의 도로 이미지와 포트홀이 있는 도로 이미지 분류하기
- 탐지모델 : 영상에서 포트홀 존재 여부와 위치를 탐지하기

　  
   
   
  
## 결론 및 시연영상
- 정확도
- GUI  



- 동영상


## 데이터셋
### 데이터셋의 구성
- 분류모델 : 정상도로 이미지 355장 + 포트홀이 있는 도로 이미지 355장
- 탐지모델 : 포트홀이 있는 도로 이미지 355장
<img width="480" alt="image" src="https://user-images.githubusercontent.com/104143807/212602714-522c5fab-ccd1-4bf4-84b3-0d53fc90820a.png">
　

### 데이터 수집방법 및 과정
#### 1. 웹크롤링 : Google, Naver, Youtube 이미지 및 영상 수집
#### 2. Data 1차 정제 
        - 포트홀이 위험한 요소가 되는 환경 -> 주로 고속 주행이 일어날 때 
            - 20km/h 이하의 저속 주행 상황의 이미지 제외
        - 사람이 포함된 이미지
        - 자동차가 불필요하게 많이 포함된 이미지
    
#### 3. Image Generation 기법 활용 : 정상 도로 , 포트홀 도로 Class 간의 데이터 불균형 해소
#### 4. Data 2차 정제 : 밝기 및 화질 저하된 불량 이미지 추가 제거
　
 
  
## 방법론
#### 1. CNN (Convolutional Neural Networks) 
##### 1) 전처리 과정

<img width="850" alt="image" src="https://user-images.githubusercontent.com/104143807/212630713-b5f4eca3-ebc5-45b0-9b96-7edebd22d91a.png">
<img width="850" alt="image" src="https://user-images.githubusercontent.com/104143807/212630871-8636173a-e6fb-45e5-bb21-e501f3fa7143.png">


##### 2) 모델 구성
##### ▷ 튜닝에 활용한 주요 하이퍼파라미터
        - CNN 계층 : CNN layer 개수, CNN 필터 개수, CNN layer 위치, activation함수
        - FC 계층 : FC layer 개수, FC layer 뉴런 개수, activation 함수  


##### ▷ 모델 구조
<img width="650" alt="image" src="https://user-images.githubusercontent.com/104143807/212631413-321b6026-a775-464b-a3db-78184d2599c5.png">

#### 2. YOLOv4
- 지역화(localization) + 분류(Classification) 동시 수행
<img width="650" alt="image" src="https://user-images.githubusercontent.com/104143807/212669219-d949c81f-d3a0-4956-bbdc-03c34ffeed59.png">

** 프로젝트에서는 발전된 기법인 YOLO v4 활용  **


#### 3. Image Generation
- **Tensorflow ImageDataGenerator** 활용하여 데이터 추가 확보
<img width="650" alt="image" src="https://user-images.githubusercontent.com/104143807/212669555-6ab2c21d-c804-4bdc-bc5d-a5660a8a0dbd.png">

　
 　  
    
## 분류 모델은 얼마나 정확히 분류할까?(다양한 척도)
### 다양한 척도로 확인하기
![image](https://user-images.githubusercontent.com/104143807/212470585-3c15b3dc-a7ea-486e-8cd8-6e5e8ea9deb7.png)


