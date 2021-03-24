# Anaconda commandline
파이썬/conda/Terminal등명령어

# Anaconda
## 새 가상환경 만들기
```
conda create --name "wordcloud' python=3.8.5
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
