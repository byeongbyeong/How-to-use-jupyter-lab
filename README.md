# Python + JupyterLab + PyTorch + CUDA 설치 가이드

AI 개발 환경 구축을 위한 **Python / JupyterLab / CUDA / PyTorch / Git 연동 설치 방법 정리**

---

# 1. Python 설치

Python 공식 사이트

https://www.python.org/downloads/

Python **3.9 버전 설치**

참고 블로그  
https://blog.naver.com/if112/222263349407

설치 시 반드시 체크

```
Add Python to PATH
```

설치 확인

```bash
python --version
```

---

# 2. JupyterLab 설치

터미널(cmd / iTerm / terminal)

```bash
pip install jupyterlab
```

회사 보안망에서 설치 실패 시

```bash
pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install jupyterlab
```

다른 라이브러리 설치도 동일

```bash
pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install <라이브러리명>
```

---

# 3. JupyterLab 실행 폴더 설정

### 1️⃣ 바탕화면에 Python 폴더 생성

```
Desktop
 └ Python
```

### 2️⃣ 해당 폴더에서

```
Shift + 우클릭
PowerShell 실행
```

### 3️⃣ 실행

```bash
jupyter lab
```

해당 폴더 기준으로 JupyterLab이 실행됨

---

# 4. CUDA 설치

CUDA 11.6 다운로드

https://developer.nvidia.com/cuda-11-6-1-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exe_local

설치 옵션

```
Windows
x86_64
Windows 10
exe(local)
```

설치 경로 예시

```
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.6
```

환경 변수 확인

```
CUDA_PATH
CUDA_PATH_V11_6
```

---

# 5. PyTorch 수동 설치

PyTorch Wheel 다운로드

Torch  
https://download.pytorch.org/whl/torch/

TorchVision  
https://download.pytorch.org/whl/torchvision/

TorchAudio  
https://download.pytorch.org/whl/torchaudio/

CUDA 11.6 + Python 3.9 버전 검색

```
cu116
cp39
```

예시 파일

```
torch-1.13.1+cu116-cp39-cp39-win_amd64.whl
```

설치

```bash
pip install torch-1.13.1+cu116-cp39-cp39-win_amd64.whl
```

보안망 환경

```bash
pip install torch-1.13.1+cu116-cp39-cp39-win_amd64.whl --trusted-host pypi.org --trusted-host files.pythonhosted.org
```

---

# 6. cuDNN 설치

다운로드

https://developer.nvidia.com/rdp/cudnn-download

버전

```
cuDNN v8.3.2
```

압축 해제 후

```
bin
include
lib
```

세 폴더를 CUDA 경로에 복사

예시

```
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.6
```

---

# 7. CUDA 사용 확인

Jupyter 또는 Python 실행

```python
import torch

print(torch.cuda.is_available())
print(torch.cuda.device_count())
print(torch.cuda.get_device_name())
```

출력 예시

```
True
1
NVIDIA RTX xxxx
```

---

# 8. JupyterLab Git 연동

설치

```bash
pip install jupyterlab-git
```

보안망 환경

```bash
pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install jupyterlab-git
```

---

# 9. JupyterLab GitHub 연동

설치

```bash
pip install jupyterlab-github
```

보안망 환경

```bash
pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install jupyterlab-github
```

---

# 10. Git 동기화 방식

JupyterLab에서 GitHub repository를 연결하면

```
GitHub Repository
        ↓
Local Folder (JupyterLab)
```

브랜치 기준

```
main
master
```

동기화 가능

---

# 설치 순서 정리

```
1 Python 설치
2 JupyterLab 설치
3 CUDA 설치
4 cuDNN 설치
5 PyTorch 수동 설치
6 CUDA 동작 확인
7 JupyterLab Git 연동
8 GitHub 연동
```

---

# 참고 링크

Python  
https://www.python.org/downloads/

CUDA  
https://developer.nvidia.com/cuda-downloads

PyTorch Wheel  
https://download.pytorch.org/whl/torch/

cuDNN  
https://developer.nvidia.com/cudnn
