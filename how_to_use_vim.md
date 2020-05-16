# Vim
Like another language, vim script is also a language. 
So it's not difficult to learn if you learn grammatical form.

## Grammatical Form
* Number - Verb - Noun
* Verb - Number - Verb - Noun
* Number - Verb
* Number - Noun

---
Vim Editor supports 6 kinds of modes.

## 1. Normal Mode

## 2. Insert Mode

#### 이동
`h`     | `j`     | `k`     | `l`
------  | ------  | ------  | ------
&#8592; | &#8595; | &#8593; | &#8594;

키  | 설명
----| ----------------------------------------------

`^` | 해당 라인 맨 앞으로 이동
`0` | 들여쓰기한 라인의 맨 앞으로 이동
`$` | 해당 라인 맨 뒤로 이동
`w` | 글자 단위로 오른쪽으로 이동
`b` | 글자 단위로 왼쪽으로 이동

#### Edit Vim Command

키  | 설명
----| ----------------------------------------------

`i` | insert 모드 실행
`a` | insert 모드 실행
`y` | 해당 라인 복사 후 clipboard에 저장
`p` | 해당 라인 복사 붙여넣기
`d` | 두번 눌렀을 때 해당 라인 삭제
`o` |
`O` | 다음 라인에 삽입

###### In Insert Mode
* Quick calculator with value insertion | Ctrol - R and "
 
#### Search Vim Command
N means the previous, and n means the following.

키  | 설명
----| ----------------------------------------------
`/` | 검색어 찾기. 
  * 엔터를 누르면 매치되는 문자열로 커서를 움직여준다.  
  * 이후 n을 누르면 결과가 있는 아래 라인으로 이동한다.

`?` | 검색어 찾기
  * 엔터를 누르면 매치되는 문자열로 커서를 움직여준다.

  * 이후 n을 누르면 결과가 있는 위 라인으로 이동한다.

`*` | 노말 모드에서 커서를 단어 위에 놓고 * 를 누르면 해당 단어로 검색어를 자동으로 만들어 검색해준다.


#### Indentation Vim Command
* 들여쓰기 | Ctrl - T
* 내어쓰기 | Ctrl - D

## 3. Visual Mode

## 4. Select Mode


## 5. Command-Line Mode

## 6. Ex Mode
