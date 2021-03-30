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
NPM에 남아있는 캐쉬 지우고 다시 시작
```
npm start --reset-cache
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
