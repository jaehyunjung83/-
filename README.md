# 이전에 RS나 RN 작업하다 지우고 다시 시작하면 100% 안됨!

## 이전 npm의 서버 작업 내용 및 포트가 살아있어서 죽인 다음에 다시 시작해야 함!!

현재 살아있는 node server 의 PID 찾기
```
(sudo) lsof -i :8081
```
```
COMMAND   PID USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
node    25762  jjh   24u  IPv6 0xb6ac2225f144d89f      0t0  TCP *:sunproxyadmin
```
PID를 찾아서 죽이기
```
kill -9 25762   (-9는 옵션)
```
그냥 켜져있는 모든 node server 다 죽이기
```
killall -9 node
```
시뮬레이터에서 앱 삭제 및 재 구축 / 실행
```
react-native start --reset-cache
```
NPM에 남아있는 캐쉬 지우고 다시 시작
```
npm start --reset-cache
```
# 오류별 대처 command

Failed to build iOS project. We ran "xcodebuild" command but it exited with error code **65**
```
xcode에서 "프로젝트명.xcworkspace 열고 build해보기, 이후 xcode에서 출력되는 오류 찾아서 수정
```
cocoapod 설치 되어있는데 cd ios에서 pod install 하면
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/x.x.x directory.
메시지 나올 때
```
sudo 등 권한의 문제가 아님!!!
rbenv global x.x.x  : ruby를 전역 버전으로 바꿔주기
```
```
vim ~/.zshrc or vim ~/.bash_profile
```
```
[[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval "$(rbenv init -)"
맨 밑에 추가 && :wq!
```
```
source ~/.zshrc or source ~/.bash_profile
```
```
gem install bundler
```
```
react-native link && cd ios && pod install && cd ..
```


# RN 프로젝트 시작 기본 command

일단 노드 설치
```
npm install
```

RN 라이브러리들과 ios, android 연결
```
react native link
```

ios에 pod설치(ios의 package.json같은건가?)하고 다시 원 루트로 돌아오기
```
cd ios && pod install && cd ..
```

ios app build
```
react-native run-ios
```
