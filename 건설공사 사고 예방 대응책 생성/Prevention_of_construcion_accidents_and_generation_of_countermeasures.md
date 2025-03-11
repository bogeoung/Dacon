# [건설공사 사고 예방 및 대응책 생성 : 한솔데코 시즌3 AI 경진대회](https://dacon.io/competitions/official/236455/overview/description)

## 환경 세팅
```

conda create -n Dacon-RAG python=3.11
conda activate Dacon-RAG
conda install pytorch=1.8.1 cudatoolkit=11.1 -c pytorch
conda install -c conda-forge huggingface_hub

```

#### ModuleNotFoundError: [No module named 'triton'](https://github.com/unslothai/unsloth/issues/964)

```angular2html
%%capture
# Installs Unsloth, Xformers (Flash Attention) and all other packages!
!pip install "unsloth[colab-new] @ git+https://github.com/unslothai/unsloth.git"

# We have to check which Torch version for Xformers (2.3 -> 0.0.27)
from torch import __version__; from packaging.version import Version as V
xformers = "xformers==0.0.27" if V(__version__) < V("2.4.0") else "xformers"
!pip install --no-deps {xformers} trl peft accelerate bitsandbytes triton
```
