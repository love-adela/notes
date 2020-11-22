`brew doctor`를 실행했을 때, CommandLineTools의 버전이 너무 낮다고 경고하는 경우가 있음. 그럴 때엔 CommandLineTools를 재설치해서 버전을 올려줘야함.

`/usr/bin/python3`로 파이썬을 실행해서 정상적으로 실행된 경우: 최소 한 개 버전 이상의 CommandLineTools가 존재함
`/usr/bin/python3`로 파이썬을 실행했을 때 "active developer path does not exist" 에러가 발생한 경우: CommandLineTools가 한 버전도 깔려있지 않은 상태

```bash
# 기존에 설치되어있던 구버전 CommandLineTools 지우는 커맨드
sudo rm -rf /Library/Developer/CommandLineTools

# 최신버전의 CommandLineTools 설치하는 커맨드, XCode 설치하는게 아니다.
sudo xcode-select --install
```