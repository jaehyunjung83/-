# Anaconda commandline
파이썬/conda/Terminal등명령어

# Anaconda
## 새 가상환경 만들기
```
conda create --name(or -n) "환경명' python=3.8.5
```
## env지우기
```
conda env remove --name(or -n) "환경명'
```
## 존재하는 가상환경 list확인
```
conda evn list
```
## 그 가상환경에 설치된 파이썬 패키지 list확인
```
conda list
```
## 가상환경 실행
```
conda activate _tika_
```
## conda로 requirement 설치
```
conda install --yes --file requirements.txt
```
## conda로 requirement 설치 안 되면 아래와 같은 메시지 출력
```
PackagesNotFoundError: The following packages are not available from current channels:

  - whitenoise==3.3.1
  - django-allauth==0.37.1
  - djangorestframework==3.9.1
  - django==2.2.13
  - django-cors-headers==2.4.0
  - django-rest-auth==0.9.3
```
## 그럼 아래처럼 개별 설치
```
conda install -c conda-forge whitenoise==3.3.1
```
## 가상환경안에 패키지 설치
```
conda install _tika_ 
```
## pip만 지원하는 패키지 설치
```
conda install pip
```
```
pip install _tika_
```
## git에서 clone한 project의 requirements.txt설치
```
while read requirement; do conda install --yes $requirement; done < requirements.txt
```
