# fastai 라이브러리의 소개

fastai 라이브러리는 현대적으로 가장 뛰어난 뉴럴넷을 빠르고 정확하게 학습시키는 방법을 간소화한다. [fastai 웹사이트](https://docs.fast.ai)를 확인해 보면, 시작하는 방법을 배울 수 있다. 이 라이브러리는 [fast.ai](http://www.fast.ai)에서 연구된 딥러닝의 가장 뛰어난 방법에 기반하고, [`vision`](https://docs.fast.ai/vision#vision), [`text`](https://docs.fast.ai/text#text), [`tabular`](https://docs.fast.ai/tabular#tabular), [`collab`](https://docs.fast.ai/collab#collab) (collaborative filtering) 관련 모델들을 지원하는 "out of the box"를 포함한다. [예제 폴더](https://github.com/fastai/fastai/tree/master/examples)에는 간단한 예제들이 담겨져 있다. 예를 들어서, [resnet18](https://arxiv.org/abs/1512.03385)를 사용하여 MNIST를 학습시키는 모델의 예제를 [여기서](https://github.com/fastai/fastai/blob/master/examples/vision.ipynb) 확인해 볼 수 있다.

```python
untar_data(MNIST_PATH)                                      # MNIST 데이터셋의 압축을 해제
data = image_data_from_folder(MNIST_PATH)                   # 압축이 해제된 MNIST 데이터를 불러와서 data 변수에 저장
learn = ConvLearner(data, tvm.resnet18, metrics=accuracy)   # CNN 학습자 생성
learn.fit(1)                                                # 학습자 실행 (학습 시작)
```

## [course.fast.ai](http://course.fast.ai) 코스를 듣는 학생들에게

`fastai`를 [course.fast.ai](http://course.fast.ai) 코스에서 사용하는 경우, `fastai 0.7.x` 버전을 사용해야 한다. 이 문서의 `fastai 1.0.x` 라고 명시된 다른 부분은 무시해도 좋다. 그리고, [여기에](https://forums.fast.ai/t/fastai-v0-install-issues-thread/24652)서 `fastai 0.7.x` 버전의 설치 방법을 따르기 바란다.

*Note: fastai v1에 대한 사용법을 리딩 개발자인 "Jeremy Howard"로부터 배우고 싶다면, "Jeremy Howard"는 [Deep Learning Part I 코스](https://www.usfca.edu/data-institute/certificates/deep-learning-part-one)를 2018년 11월 22일부터 샌프란시스코 대학교에서 가르칠 계획이 있다.

## 설치 방법

`fastai-1.x` 는 `conda` 또는 `pip`라는 패키지 매니져, 그리고 소스코드를 직접 빌드해서 설치가 가능하다. 요구되는 올바른 `pytorch` 버전이 우선적으로 인스톨 되어야 하기 때문에, 아직까지는 단순히 *install*을 실행하지 못한다. 따라서, `fastai-1.x`를 설치하기 위해서는 아래의 방법 중 한가지를 선택해서 진행해야만 한다.

[최근의 NVIDIA 그래픽 카드](https://www.geforce.com/hardware/technology/cuda/supported-gpus)를 사용하고 이에 대한 NVIDIA 드라이버가 잘 설정 되어 있다면, GPU 설치 가이드를 따라해보길 바란다. 그렇지 않다면, CPU 설치 가이드를 확인해 보자.

`fastai`와 관련된 의존 패키지들을 가상 환경([`conda`](https://conda.io/docs/user-guide/tasks/manage-environments.html) 또는 그외)에 설치하는 것이 가장 추천되는 방법이다. 왜냐하면, 시스템 레벨에 설치된 파이썬 패키지와의 충돌과 같은 부분을 신경쓰지 않아도 되기 때문이다. 반드시 그래야 한다는 것은 아니지만, 관련 패키지 의존성에 대한 문제를 겪게 된다면, `fastai`만을 위한 가상 환경의 사용을 고려해보길 바란다. 

### Conda Install (추천)

* GPU

   ```sh
   conda install -c pytorch pytorch-nightly cuda92  # 파이토치 및 쿠다 라이브러리 설치
   conda install -c fastai torchvision-nightly      # fastai에서 수정된 파이토치 vision 라이브러리 설치
   conda install -c fastai fastai                   # fastai 라이브러리 설치
   ```

* CPU

   ```sh
   conda install -c pytorch pytorch-nightly-cpu     # CPU 버전의 파이토치 설치
   conda install -c fastai torchvision-nightly-cpu  # fastai에서 수정된 파이토치 vision 라이브러리 설치
   conda install -c fastai fastai                   # fastai 라이브러리 설치
   ```


### PyPI Install (비추)

* GPU

   ```
   pip install torch_nightly -f https://download.pytorch.org/whl/nightly/cu92/torch_nightly.html
   pip install fastai
   ```

* CPU

   ```
   pip install torch_nightly -f https://download.pytorch.org/whl/nightly/cpu/torch_nightly.html
   pip install fastai
   ```

위 설정은 `torch-1.x`을 지원하는 `torchvision-nightly` 또한 설치를 수행하게 된다.

### 개발를 위한 설치 방법

우선, 위에 명시된 `PyPi` 또는 `Conda`에 대한 설치 방법을 수행한다. 그리고 나서, `fastai` 패키지를 `pip uninstall fastai` 또는 `conda uninstall fastai`와 같은 명령어로 삭제한다. 마지막으로 [pip editable install](https://pip.pypa.io/en/stable/reference/pip_install/#editable-installs)를 사용하여 삭제된 `fastai` 패키지를 재 설치 한다.

```sh
git clone https://github.com/fastai/fastai  # fastai의 소스코드 내려받기
cd fastai                                   # fastai 소스코드 폴더로 이동
tools/run-after-git-clone                   # tools 폴더에 있는 run-after-git-clone 명령어 수행
pip install -e .[dev]                       # 설치
```

빌드 결과가 잘 동작하는지 주피터 노트북을 통해서도 확인해 볼 수 있다:

```
jupyter notebook
```

위 명령어는 주피터 노트북 관리 페이지를 실행하게 된다. 여기서, `examples/tabular.ipynb`와 같은 한가지 예제 노트북을 실행시켜 보자. 

또는, 빨리 빌드 결과를 확인해 보고 싶은경우, CLI를 통해서도 가능하다:

```
jupyter nbconvert --execute --ExecutePreprocessor.timeout=600 --to notebook examples/tabular.ipynb
```

[CONTRIBUTING.md](https://github.com/fastai/fastai/blob/master/CONTRIBUTING.md)와 [develop.md](https://github.com/fastai/fastai/blob/master/docs/develop.md)를 참조하면 `fastai` 프로젝트에 기여하는 방법에 대해서 더 자세한 것을 확인할 수 있다.

### 소스코드를 통한 빌드

어떤 이유에서든, 소스코드를 직접 빌드해야 한다면 아래 설명을 확인해 보기 바란다.

1. [파이토치의 완전한 설치 가이드](https://github.com/pytorch/pytorch#from-source)에서 소스코드를 직접 빌드하여 `pytorch`를 설치하는 방법을 확인해 볼 수 있다. 기억해야 할 건, 우선적으로 CUDA, CuDNN, 그리고 다른 필수적으로 요구되는 라이브러리들이 먼저 설치 되어야만 한다.

2. 다음으로는, `torchvision`을 소스코드를 통해서 빌드해야한다.

   ```sh
   git clone https://github.com/pytorch/vision  # torchvision의 소스코드 내려받기
   cd vision                                    # 해당 폴더로 이동
   python setup.py install                      # 설치
   ```

3. `pytorch`와 `torchvision` 모두 잘 설치되었다면, 이 설치된 라이브러리가 잘 불러와 지는지를 확인해 보자:

   ```python
   import torch
   import torchvision
   ```
   
   마지막으로, 위의 앞 섹션에서 설명된 설치방법을 통해서 `fastai`를 pip 또는 conda 또는 소스코드를 통하여 설치하면된다. 


## 설치 관련 이슈사항

설치 과정이 실패하는 경우, 일단 [사용중인 시스템이 지원되는지](https://github.com/fastai/fastai/blob/master/README.md#is-my-system-supported)를 확인해 본다. 만약 문제점이 아직 해결되지 않는다면, [트러블슈팅 문서](https://docs-dev.fast.ai/troubleshoot)를 확인해보길 바란다.

conda에서 설치 문제를 겪고 있다면, 가장 최근 버전의 `conda`가 설치되어 있는지 확인해 본다:
```sh
conda update conda
```

아래의 명령어로도 동일한 것을 수행할 수 있다:
```sh
conda install conda
```


### 사용하는 시스템이 지원대상인가?

1. Python: python 3.6 또는 그 이상의 버전

2. CPU 또는 GPU

   `pytorch` 바이너리 패키지는 자체적인 CUDA, CuDNN, NCCL, MKL, 그리고 다른 라이브러리와 함께 설치되기 때문에, 시스템-레벨의 NVIDIA CUDA와 관련 라이브러리를 직접 설치하지 않아도 된다. 만약 이미 설치되었다고 해도, 어떤 버전의 NVIDIA CUDA 라이브러리가 시스템-레벨에 설치 되었는지는 신경쓰지 않아도 된다. 시스템-레벨에서 이미 CUDA 9.0 라이브러리가 설치되어 있더라도, 여전히 `pytorch`를 `cuda 9.2` 라이브러리와 함께 문제 없이 사용 가능하다. 

   단 한가지 요구사항은 NVIDIA 드라이버를 올바르게 설치하고 설정해둬야 한다는 것이다. 일반적으로, `nvidia-smi`라는 명령어를 실행해서 이를 테스트 해 볼 수 있다. 사용하는 시스템에 `nvidia-smi` 라는 어플리케이션이 없을 수 있는데, 이는 NVIDIA 드라이버가 적절하게 설정되지 않았을 확률이 매우 높음을 의미한다. 기억해 둬야할 부분으로는, NVIDIA 드라이버는 설치된 이후, 방드시 재부팅이 이루어져야 한다는 것이다.

3. 운영체제:

   fastai-1.0은 pytorch-1.0을 사요하므로, pytorch-1.0을 우선적으로 설치할 수 있어야만한다.

   지금 현재 시점에서, pytorch.org의 pre-1.0.0 버전인 (`torch-nightly`)가 지원되고 있다:

    | Platform | GPU    | CPU    |
    | ---      | ---    | ---    |
    | linux    | binary | binary |
    | mac      | source | binary |
    | windows  | source | source |

   레전드: `binary` = 바로 설치가 가능함, `source` = 소스코드를 직접 빌드해야 설치 가능함.

   `pytorch` 1.0.0 가 출시되고, 설치가능한 패키지들이 공개될때, 위 내용은 수정될 수 있다. 그렇게 되기까지 시간이 약간 걸릴 것인데, 다음의 [공식 업데이트 확인 웹사이트](https://pytorch.org/get-started/locally/)를 통해서 그 시기를 확인해 볼 수 있다.

   사용중인 시스템에서 `pytorch` 프리뷰 버전이 conda 또는 pip의 패키지에 존재하지 않는다면, 여전히 이 버전의 소스코드를 [직접 빌드](https://pytorch.org/get-started/locally/)해 볼 수 있다.

## 히스토리

자세한 변경사항은 [여기서](https://github.com/fastai/fastai/blob/master/CHANGES.md) 확인이 가능하다.

## Copyright

Copyright 2017 onwards, fast.ai, Inc. Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. A copy of the License is provided in the LICENSE file in this repository.
