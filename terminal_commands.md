---
layout: post
title:  리눅스 터미널 사용 위키
category: Wiki
tags: [computer]
---
## Linux Command
### 1. Navigating the File System
* ```$``` : shell propmt라고 부른다.
* ```ls``` : lists의 줄임말. 현재 위치(working directory)에서의 폴더와 파일을 보여준다. ```.```로 시작하는 파일 이름은 감춰진다.

#### 1.1 Options Modifying the Behavior of Commands
* ```ls -a``` : "```-a```" 옵션은 ls 명령의 동작을 수정하여 ```.```으로 시작하는 파일과 디렉토리를 나열한다.
* ```ls -l``` : "```-l```" 옵션은 디렉토리의 모든 내용을 긴 형식으로 테이블로 나열한다.
* ```ls -t```: "```-t```" 옵션은 파일 및 디렉토리를 마지막으로 수정한 시간까지 주문한다.
* ```ls -alt```: "```-alt```" 옵션에는 숨김 파일 및 디렉토리를 포함하여 마지막으로 수정한 날짜와 시간에 따라 긴 형식으로 모든 내용이 나열되어 있다.

* ``` ls -G -al ```

### 2. Viewing and Changing the Filesystem
#### 2.1 To Navigate through files and folders
* ```pwd``` : 현재 작업 디렉토리 출력(print working directory)
* ```cd``` : 디렉토리 변경(change directory)
* ```cd .. ``` : 이전 디렉토리로 돌아가기
* ```mkdir``` : 디렉토리 생성(make directory)
* ```touch``` : 현재 작업 디렉토리 안에 새로운 파일 생성

* pasteboard를 활용하여 코드를 copy-paste
    * pbcopy < example.py
        * example.py의 내용을 pasteboard에 복사하기
    * pbpaste > a
        * a에 example.py의 내용을 붙여넣기


#### 2.2 To Change Files and Directories
* ```cp ```: 파일과 디렉토리의 내용을 복제(copy)
    * 사용법 : cp biopic/cleopatra.txt hisotircal/

* ```mv``` : 파일을 디렉토리로 이동(move)
    * 사용법 : mv wonderwoman.txt captain_marvel.txt superhero/

* ```rm``` : 파일과 디렉토리를 삭제(remove) 
    * 주의사항 : 파일과 디렉토리를 영구적으로 삭제하게 된다.
* ```rm -r```: "```-r```" 옵션은 "``` rm ```"명령어의 동작을 수정. recursive의 약자로 디렉토리와 모든 하위 디렉토리를 삭제하는데 사용된다.

### 3. Redirecting Input and Output
* ```echo "Hello"```

* stdin : 키보드나 입력 장치를 통해 단자에 입력되는 정보
* stdout : 프로세스가 실행된 후 출력되는 정보 
* stderr :실패한 프로세스에 의해 출력되는 오류 메시지
* 리디렉션은 표준 입력, 표준 출력 및 표준 오류를 다른 위치로 또는 다른 위치로 다시 라우팅함.

* ```cat``` : cat 명령은 파일의 내용을 터미널에 출력

#### 3.1 Common Redirection Commands

* ```>``` : > 왼쪽에 위치한 명령어의 표준 출력을 > 오른쪽의 파일로 리디렉션
    * ```cat oceans.txt > continents.txt```명령어를 실행하면 oceans.txt의 내용이 continents.txt에 덮어쓰여, oceans.txt 내용만 확인할 수 있다.

* ```>>``` : >> 왼쪽의 명령어 표준 출력 내용을 >> 오른쪽 파일에 추가한다.

* ```|``` : pipe라고 부른다. ``` | ``` 왼쪽 명령의 표준 출력을 취해서 오른쪽 명령의 표준 입력으로 파이프화 한다. '명령에 대한 명령'의 리디렉션이라고 생각할 수 있다.
* ```wc``` : ?

#### 3.2 Other Commands combined with redirection commands

* ``` sort ``` : 표준 입력을 취하여 표준 출력 형태로 알파벳 순으로 정렬한다.
* ```uniq``` : 파일의 중복된 라인을 필터링 한다.
    * 사용법 : ``` sort deserts.txt | uniq uniq-deserts.txt ```
* ```grep |``` : global regular expression print의 줄임말이다. 패턴과 일치하는 행의 파일을 검색해 결과를 보여준다. 대소문자를 구분한다.
* ```grep -i``` 에서 ```-i``` 옵션은 대소문자를 구분하지 않도록 한다.
* ```grep -Rl```은 디렉토리의 모든 파일을 검색하고 일치하는 결과를 가진 파일 이름만 출력한다. ```-R```은 "recursive"를 의미하고, ```l```은 "일치하는 파일"을 의미한다.
* ```sed```는 "stream editor"를 의미한다. 표준 입력을 받아들여 표현식을 기반으로 수정한 후 출력 데이터로 표시한다. "[find](find) and replace"와 유사하다.
- 사용법 : ```$ sed 's/snow/rain/g' forests.txt ```
### 4. Configuring the Environment

* file 관리
    * file 삭제 : ```rm -rf 파일명```

### 5. To Execute 
* python files : ```python3 gcd.py```
* input file : ```python3 example.py < input```
* Python Virtual Environment
    * activate: ```source myvenv/bin/activate```
    * deactivate : ```deactivate```
* editor program :
    * vsCode : ```code 파일명.확장자```
        * 새 파일 열기: ```code .```

### 6. find

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

## Git Command
[TBW]
* glgoa : ```git log --oneline --decorate --graph --all```

* ```git status```
* ```git show```
* ```git show HEAD~1```
* ```git rm -r venv```
* ```git commit -v```

* ```git fetch```
* ```git push```

