# 배경

in memory에 정보를 캐싱해서 쓰고 싶을 때, 여태까지 전역 변수를 활용했었습니다.
하지만 매번 그걸 만드는 것은 비효율적이었습니다.
바퀴가 있는데 다시 만들 필요가 있을까요.
전체적으로 어떻게 돌아가는지 이해하고 그 기술을 가져다 쓰는 것이 최선인 것 같습니다.

여기서는 fastapi_cache라는 모듈을 활용해 in-memory caching을 하는 방법을 실험해보려고 합니다.

# 실행 준비

우선 이 예제를 위해 활용한 Python의 버전은 `3.8.16`입니다.
레포에 포함된 .python-version 파일에 이 버전이 명시되어있습니다.
이 파일은 [pyenv](https://github.com/pyenv/pyenv)에서 사용하는 파일입니다.
pyenv는 nvm처럼 원하는 버전의 python을 간편한 명령어로 설치하고 활용할 수 있는 도구입니다.

pyenv를 잘 설치하고 설정했다면, 아래 명령으로 설치하고 이 디렉토리로 오면 버전이 자동으로 바뀔 것입니다.

```
pyenv install 3.8.16
```

이제 아래 명령어로 가상환경을 구성합니다.

```bash
python -m venv venv
```

아래 명령어로 가상환경을 해당 쉘 세션에서 활성화 시킵니다.

```bash
source venv/bin/activate
```

다음 명령어로 필요한 패키지를 설치합니다.

```bash
pip install -r requirements.txt
```

# 실행

```bash
uvicorn main:app --reload
```
