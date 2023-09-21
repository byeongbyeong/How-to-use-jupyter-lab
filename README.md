# How-to-use-jupyter-lab

파이썬 설치 및 주피터랩 설치 파이토치 수동 설치 주피터랩에서 깃배쉬나 깃허브 연결시키기 등 정보 적어봅니당

https://www.python.org/downloads/ 파이썬 설치 (https://blog.naver.com/if112/222263349407) 3.9버전 설치

cmd / iTerm / terminal
-> pip install jupyterlab 회사 서버보안 때문에 안되면 pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install <라이브러리jupyterlab(다받을거)>

설치완료후 바탕화면에 파이썬 폴더 만들고 폴더내에서 shift 키 우른 채 왼쪽 클릭하여 파워셀 실행 jupyter lab 파이썬 폴더에 저장됌.

설치완료후 cmd 에 jupyter lab 대신 저장경로 설정


파이토치 수동설치 https://download.pytorch.org/whl/torch/ cu116-cp39 (ctrl+F) 제일 밑에거 윈도우용 https://download.pytorch.org/whl/torchvision/ https://download.pytorch.org/whl/torchaudio/ 링크 클릭 설치

cmd에서 설치 명령어 pip install "torchaudio-0.13.1+cu116-cp39-cp39-win_amd64.whl" --trusted-host pypi.org --trusted-host files.pythonhosted.org "다운로드 받은 파일명"

cuda 11.6 설치 https://developer.nvidia.com/cuda-11-6-1-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exe_local windows x86_64 10 exe(local) Ex) C:\Users\AppData\Local\Temp\CUDA (설치한 쿠다 경로) 시스템 환경 변수 편집 - 시스템 변수에 cuda path 확인

주피터로 cuda 사용가능한지 확인 print(torch.cuda.is_available()) #쿠다 사용가능한지 확인 불가하면 false print(torch.cuda.device_count()) #이용가능한 그래픽카드 수 print(torch.cuda.get_device_name()) #사용중인 그래픽카드

cuDNN v8.3.2 nvidia 회원가입후 https://developer.nvidia.com/rdp/cudnn-download#a-collapse714-92 에서 해당하는 것 다운로드 후 집파일 압축 해제 폴더 내 bin/include/lib 폴더 CUDA 파일 있는 경로에 추가 (CUDA폴더 내 bin/include/lib에 복사)

jupyterlab - git 연결 pip install jupyterlab-git or pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install jupyterlab-git

jupyterlab - github 연결 pip install jupyterlab-github or pip --trusted-host pypi.org --trusted-host files.pythonhosted.org install jupyterlab-github

jupyterlab 내에서 main/master에 따라 로컬 폴더 내용 변경됌
