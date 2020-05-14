# Terminal commands

## find 명령어

예시 : `find . -type f -exec grep "example" '{}' \; -print `

### 찾기 옵션

`find` 는 메타파일 이름 기반으로 찾아주는 것이기 때문에 파일 내용을 검색할 수 없음. 

파일과 디렉토리 구분하는 옵션

* file : `find . -type f`
  * . 혹은 현재 파일 이름을 기입
* directory : `find . -type d`
    * . 혹은 디렉토리 이름을 기입

매칭되는 파일 목록 보는 옵션

* `-print`
* 앞의 명령어와 구분하기 위해서 \;를 사용한다.

find exec 대신 `find . | xargs`로 대체할 수 있음. 생활에 필요한 것 먼저 사용해보면서 사용법 늘려가좌.