# 소개

이 저장소는 Fast.ai 에서 제공되는 무료 교육용 컨텐츠에 대한 스터디 목적으로 개설되었고, 다음의 스터디 목적을 가진다.

- **Fast.ai에서 제공하는 컨텐츠의 한글화**
  - Fast.ai 라이브러리 소개 및 설치법
  - Fast.ai의 교육용 주피터 노트북 자료의 한글화
    - 레슨의 총 수는 14개로 구성된다
  - Fast.ai의 코스 비디오 컨텐츠 자료의 자막 한글화
    - 현재는 딥러닝 코스만을 타겟으로 한다.
    - 추후 상황에 따라서 머신러닝 코스도 포함 결정.

- **이외의 것**
  - 각 교육 레슨별 추가적인 프로젝트 수행
  - 스터디 및 프로젝트 수행 과정에서, 학위로 이어지거나 단순 개인적인 이유의 흥미로운 연구주제 발굴

다음은 Fast.ai 공식 자료에 대한 링크를 나열한다.

- [Fast.ai 공식 홈페이지](https://www.fast.ai/)
- [Fast.ai 딥러닝 코스 홈페이지](https://course.fast.ai/)
- [Fast.ai 커뮤니티 포럼](https://forums.fast.ai/)
- [Fast.ai 저장소(라이브러리, 코스등)](https://github.com/fastai/fastai)

# 작업중인 자막을 입혀서 시청하는 방법

1. 로컬 컴퓨터에서 시청하는 방법
   - 1.1 Youtube 동영상 다운로드
   - 1.2 저장소에 등록된 sbv 자막 다운로드
   - 1.3 로컬 컴퓨터의 동영상 플레이어로 재생

2. Youtube 에서 바로 시청하는 방법
   - 2.1 강의 sbv 자막 파일 다운로드
   - 2.2 강의 링크로 Youtube에 호스팅된 강의로 이동
   - 2.3 Youtube 동영상 플레이어 하단의 톱니바퀴 아이콘 클릭
   - 2.4 Subtitles/CC 메뉴 선택 ==> Add subtitles/CC 선택 ==> Creator Studio로 이동됨
   - 2.5 동영상 우측의 Select Language 메뉴 선택 ==> Korean 선택 ==> 자막 추가하는 주소로 이동됨
   - 2.6 동영상 좌측의 Actions 메뉴 선택 ==> Upload a file 선택 ==> sbv 자막파일 선택
   - 2.7 자막이 입혀진 동영상 시청

# 컨텐츠

- **[Fast.ai 라이브러리 소개 및 설치법](./fastai_lib_intro.md)**
- **Fast.ai 교육용 컨텐츠**
  - 파트1
    - 레슨1: 고양이와 강아지를 인식해 보자
      - [강의 동영상](https://www.youtube.com/watch?v=IPBSB1HLNLo) | [자막](./lesson1.sbv)
      - 주피터 노트북: [레슨1](./courses/dl1/lesson1.ipynb)
    
    - 레슨2: 컨볼루션 뉴럴 네트워크를 사용해 보자
      - [강의 동영상](https://www.youtube.com/watch?v=JNxcznsrRb8&t=5630s) | [자막](./lesson2.sbv)
      - 주피터 노트북: [개 품종 분류 경연(dog breed classification)](./courses/dl1/lesson1-breeds.ipynb) | [ResNext50 개 vs 고양이](./courses/dl1/lesson1-rxt50.ipynb)
      
    - 레슨3: 인식 알고리즘의 성능을 향상시켜 보자
      - [강의 동영상](https://www.youtube.com/watch?v=9C06ZPF8Uuc) | [자막](./lesson3.sbv)
      - 주피터 노트북: [Keras 사용](./courses/dl1/keras_lesson1.ipynb) | [다중-레이블 문제(planet 경연)](./courses/dl1/lesson2-image_models.ipynb) | [Rossman 판매량 데이터](./courses/dl1/lesson3-rossman.ipynb)
    
    - 레슨4: 사람의 언어를 이해하는 모델을 사용해 보자
      - [강의 동영상](https://www.youtube.com/watch?v=gbceqO8PpBg&t=283s) | [자막](./lesson4.sbv)
      - 주피터 노트북: [Rossman 판매량 데이터](./courses/dl1/lesson3-rossman.ipynb) | [IMDB](./courses/dl1/lesson4-imdb.ipynb)
    
    - 레슨5: 필터를 적용해 보자
      - [강의 동영상](https://www.youtube.com/watch?v=J99NV9Cr75I) | [자막](./)
    
    - 레슨6: 임베딩 기술과 RNN (리커런트 뉴럴 네트워크)
      - [강의 동영상](https://www.youtube.com/watch?v=sHcLkfRrgoQ&t=1s) | [자막]
    
    - 레슨7: ResNet 이라는 모델을 이해해 보자
      - [강의 동영상](https://www.youtube.com/watch?v=H3g26EVADgY&t=11s) | [자막]

  - 파트2
    - 레슨8: 사물을 인식해 보자 (이미지의 어디에 사물이 있는지 위치)
    - 레슨9: SSD라는 사물인식 알고리즘을 이해하고 사용해 보자
    - 레슨10: 자연어처리의 기본 및 전이학습을 해보자
    - 레슨11: 언어간 번역(영어-프랑스어 같은)을 해보자
    - 레슨12: GAN으로 컴퓨터가 생성하는 진짜같은 이미지
    - 레슨13: GAN의 일 종인 CycleGANs을 이해해 보자
    - 레슨14: 저해상도 이미지를 고해상도로 보정해주는 Super Resolution을 이해해보자. 또, 이미지에서 사물별로 색깔을 칠해서 세그먼테이션을 ...
