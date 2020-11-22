# 2019-05-17

### Absolute path and Relative path
* https://en.wikipedia.org/wiki/Path_(computing)#Absolute_and_relative_paths

An absolute or full path points to the same location in a file system, regardless of the current working directory.
To do that, it must include the root directory.

By contrast, a relative path starts from some given working directory, avoiding the need to provide the full absolute path. 
A filename can be considered as a relative path based at the current working directory. 
If the working directory is not the file's parent directory, a file not found error will result if the file is addressed by its name.

### Unix Command

| Command | Meaning | Usage |
| ------- | ------- | ----- |
| `mv`    | move    | * Move files or directories from one place to another |
                      * If both filenames are on the same filesystem, file rename |
### Process 이동
* fg : forground
* ctrl + z : background

## 2019-05-19 
* 코테에서 시간복잡도가 뭐냐고 무조건 물어본당
* Amortized (Accounting) 와 Big(O)의 차이를 들어 설명해야 한다
* 

### Big(O)
#### Limit of a function
극한의 정의에 따라 최고차항으로 극한값을 구하는 방식을 Big(O) Notation에 활용한다.
* n -> 무한대로 갈 때 lim f(n) = 3을 그래프로 나타내보자.
* ε(입실론(실수)) : 함숫값과 극한값의 차. 차이의 상한. 예를 들어 어떤 시점부터는 ε이 0.01 이상으로 안 생긴다.
  * δ????
  * 임의의 ε에 대해 N보다 큰 모든 n에 대해, |f(n) - 3| < ε 를 만족시키는 N이 항상 존재한다.
  * ε 표기로 극한 정의  : For every real ε > 0, there exists a real δ > 0 such that for all real x, 0 < | x − p | < δ implies | f(x) − L | < ε.

무한대 정의하지 말자. 
* n -> 무한대로 갈 때 
* 임의의 K ∈ R에 대해 "For every real x > k, f(x) > K"가 성립하는 k가 존재한다.

#### Big(O) Notation
충분히 큰 N ∈ R에 대해 "For evry real n > N, f(n) < k n ** 2(**상한**)"가 성립하는 k가 존재한다.
* (x) = O( g(x) ) as x → k if there exist positive constants δ and C such that f(x) ≤ C g(x) for all x such that |x – k| < δ.
* 이 알고리즘이 제일 느려도 이거보다 느릴 수 없다.
=> 관례적으로 쓰이는 이유 : 가장 빠른 것보다 가장 느린 것에 관심을 가진다.
#### Big(Ω) Notation
충분히 큰 N R에 대해 "For every real n > N, f(n) > k n ** 2n" (**하한**)가 성립하는 k가 존재한다.
* f(x) = Ω( g(x) ) as x → k if there exist positive constants δ and C such that f(x) ≥ C g(x) for all x such that |x – k| < δ.
* f(x) = Ω( g(x) ) as x → k if there exist positive constants δ and C such that f(x) ≥ C g(x) for all x such that |x – k| < δ.
* 이 알고리즘이 제일 느려도 이것보다 빠를 수 없다.

#### Big(Θ) Notation
충분히 큰 N R에 대해 "For every n > N, a n ** 2 < f(n) < b n ** 2"가 성립하는 a, b 존재한다. (상하한)
* Θ 를 정의하기 어려울 때가 많아서, Big(O)을 사용한다.

#### Big() Notation

* f(x) = ο( g(x) ) as x → k if the limit as x → k of f(x)/g(x) is 0.

* f(x) = ω( g(x) ) as x → k if the limit as x → k of f(x)/g(x) is ∞.


### Memory
* C와 C++에서는 malloc()이라는 라이브러리로 원하는 메모리를 확장한다.
* Dynamic doubling: 
* Python
  * a = [1, 2, 3]
  * a.push(4)의 시간 복잡도는? 
    * O(n)
    * Ω(1)
    * Θ()는 찾을 수 없다.

### Splay
* Balanced Tree 중에서 가장 구현하기 쉽다.
* splaying : 라인 이모티콘 추천 알고리즘 (자주 쓰는 것이 앞에 잘 안 쓰는 것이 뒤로)
* 덜 읽히는게 leaf로.
* 경우의 수 : 3가지
* insert, delete, update
* 문제 풀 때 응용하기 쉽다. (AVL, RB, 2-3-4, B, B+에 비해서)

### HashMap
* O(Nl _ M) : Amortized
  * 시간복잡도 2위
### Trie
* O(MlogM + logM * Nl)
  * 시간복잡도1위
* Variation을 줄 때 조금 더 자유롭다.
  * Hashmap 같은 

### BST
* O(Nl + logNM)
  * 시간복잡도 3위

#### Trie
* 발음 [trai:]
* N진트리
* 정규표현식
* Prefix Tree (앞 글자, 뒷글자 둘 다 할 수 있다.)
* Suffix Tree
* 언제 쓰나?
  * 지지지지지지지현
Radix Sort와 비슷하다. 
  * String이나 Number을 정렬할 때 꼭 순서대로 할 필요 없음.
  * 2진수로 표현하면 무조건 Binary Tree
    * Bit-wise Trie
      * 0111000011011
           /     \
	00001    10000   
* 정렬과 BST는 비슷~

* 쓰이는 때 : 

* Mutable로 짜자. BST는 immutable로.
* 자식은 무조건 is_match = True

class Trie:
    def __init__(key:str):
        # hashmap
        self.children = {} # hashmap (depth를 1로 하면)
        self.key = key
	self.is_match = True

    def find(query:str, k:int=1):
        next = self.children.get(query[:k])
	if next is None:
	    return find.next(query, k+1)

    def add():
        # TODO: 기존에 있었던 항목을 add시키는 경우 is_match를 잘 설정해주자.
	# TODO: add하고 is_match 잘 설정해주자.

    def delete():
        # 잘 안 나온다.
        # TODO : 자식이 하나인 부모를 재귀적으로 삭제.
	# TODO : is_match를 삭제할 수도 있다.
# 사용법을 먼저 상상한다음 안 쪽을 채워넣으세여.
trie = Trie("app")
trie = Trie("api") 

### 2019-05-24
The connection has timed out
+, * 의 차이점 
  * + : 1 이상
  * * : 0 이상

### 2019-06-03
* Server Information
  * ``` ssh botanicgirl@14.63.28.44 ```
  * ``` sudo python3 -m http.server 80 ```
    * build 하고 싶은 디렉토리에 갈 것

* TMUX
  * 

* Domain
  * Cloudflare Registrar가 ICANN에 도메인을 대신 사줌
  * https://www.cloudflare.com/products/registrar/

* TTY
  * https://en.wikipedia.org/wiki/Tty_(unix) 
* Raspberrypi3 
  * On/ Off
    * ``` sudo systemctl poweroff```
  * 용량 확인
    * ```lsblk```
* IP
  * IP Address 확인 : ``` ip addr show ```

### 2019-06-05
* 오타 발견 : https://veranostech.github.io/docs-korean-sphinx/doc/_build/html/usage/quickstart.html
* Vim
  * 여러 줄을 한 꺼번에 다룰 때
  * Visual Mode 선택 -> 블록 지정 -> Shift + I -> 띄워쓰기 -> Esc 2번 누르기

### 2019-06-06

#### Git

- Git 저장소 만들기

```
$ git init
Initialized empty Git repository in

$ git config --global user.name "love-adelar"
$ git config --global user.email love.adelar@gmail.com
```

- .gitignore 만들기

- 변경된 사항 확인하기
```
$ git status
```
- 저장소에 코드 넣기
```
$ git add -i
$ git commit -m ""
```

- git 저장소를 github 저장소에 연결하기
```
$ git remote add origin git@github.com:love-adelar/adela.love.git
```

- push 하기
```
git push -u origin master
```

- Git public Key 생성하기
```

```

- Github settings에 Mimosa용 public key 생성하기


### 2019-06-09
* 로컬에서 서버로 이미지 보내기
  * scp


### 2019-06-11
* Terminal key

* ctrl + a : 맨 앞으로
* ctrl + e : 맨 뒤로
* ctrl + f : 한 글자 앞으로
* ctrl + b : 한 글자 뒤로
* esc + f : 한 단어 앞으로
* esc + b : 한 단어 뒤로
* !py + tab : 앞서 쳤던 명령어 

* ctrl + l : 화면 수직분할


### 2019-06-15

else를 쓰지 않기 위해 if에서 return 을 사용한다.
```
if 조건:
    실행문B
    return
실행문A
```

* 실행문 B가 짧을 때
```
if  조건:
    실행문B
else:
    실행문A
```
* 실행문 A가 짧을 때
```
if not 조건:
    실행문A
    return
실행문 B
```


* for 문을 사용할 때 flag를 사용하는 이유 : 전체를 돈 후 상황을 알 수 없어서.

#### 19-06-30

* for 문 돌릴 때 10억초 소요

#### 19-07-03

```
But this is of little avail. Though this is, strictly speaking, a syntactically correct Python statement, it doesn’t do much of anything useful. In particular, it does not place any of the modules in pkg into the local namespace:

>>> pkg.mod1
Traceback (most recent call last):
  File "<pyshell#34>", line 1, in <module>
    pkg.mod1
AttributeError: module 'pkg' has no attribute 'mod1'
>>> pkg.mod1.foo()
Traceback (most recent call last):
  File "<pyshell#35>", line 1, in <module>
    pkg.mod1.foo()
AttributeError: module 'pkg' has no attribute 'mod1'
>>> pkg.mod2.Bar()
Traceback (most recent call last):
  File "<pyshell#36>", line 1, in <module>
    pkg.mod2.Bar()
AttributeError: module 'pkg' has no attribute 'mod2'

```
To actually import the modules or their contents, you need to use one of the forms shown above.

link : https://realpython.com/python-modules-packages/#python-packages


### 2019-07-14

1. 브랜치를 만든다.
```git checkout -b <branch name> # branch 만들기 및 해당 branch로 이동```

2. 마스터에 있는 파일을 직접 수정하지 말고 로컬 파일을 수정한다.
3. git에 파일을 올린다.
```git add <file>```

4. Commit Message 작성
```git commit -m "blahblah"```

5. Pull request
```git push --set-upstream origin adela```

6. (해도 되고 안 해도 됨) 브랜치 삭제하기
 * master branch로 이동
```git checkout master```

 * 만든 branch 삭제
```git branch -D <branch주소>```

### 2019-10-09

unittest에서는 클래스를 작성할 때마다 unittest.TestCase 클래스를 상속 받아야 하거나 assertEqual 등의 비교문을 사용해야 하는 등 보일러플레이트가 많다.
pytest는 fixture를 별도의 함수로 분리해서 관리하고, 필요한 테스트 케이스에서만 호출해서 사용할 수 있다.
따라서 fixture를 모듈화, 재가공, 재사용하기 쉽다.

### 2019-10-4


# 회원가입
# 회원가입 페이지 테스트
# - url 제대로 셋팅되어 있나?
# - 회원가입 view를 따로 붙인다면 붙이고나서 200이 떨어지는지 테스트

# 회원가입 페이지 제대로 뜨는가?
# - 회원가입시 필요한 데티어가 HTML에 박혀 있나
# - 회원가입 form 에 입력이 되나

# 테스트를 손으로 짜지 않게 하자.
# 손으로 테스트해야 할 때가 있긴 있다. 내 코드에 확신이 없을 때.

# 요구사항 정리
# functional test로 정리하고 구현도 하기.
# - functional test 한 개씩 돌려보고
# - 실패하면 unit test로.
# - 브라우저 띄우기.

# Mistune에 리스트를 넣으면
# 렌더링하는 전용 function을 따로 만들어서 테스트.
# 기본적인 html 문법 -> beautifulsoup으로 파싱해서 검사하거나.

# Todo
# - 실패하는 케이스를 짜기.
# - pytest-django, model-mommy, factory-boy <= 코드를 편하고 짧게 쓸 수 있는지.
# - Coverage
# - Blog


### 2019-10-16

#### 1 
수강생 분이 .csv 파일 전체를 올리시느라 git에서 용량 제한 메시지를 받으셨다고 하셨다. 이를 해결하기 위해 .gitignore 파일에 이를 집어넣었는데, 이미 과거에 큰 파일을 커밋했던 기록이 있어서 push가 되지 않는 문제가 있었다. 또 commit이 어딨는지도 모르는 상태.

(1) large file을 넣을 수 있는 git extension이 있다. https://git-lfs.github.com/
(2) commit을 찾기 위해 `git reflog --stat`을 사용했다.
(3) commit을 수정 또는 삭제할 수 있는데, 수정하는 경우 `git rebase -i`를 써야 했고, 삭제하는 경우엔 https://help.github.com/en/articles/removing-sensitive-data-from-a-repository 를 참고하면 되었다. 후자의 테크닉은 보안이 높은 파일을 실수로 올렸을 경우 이 커밋을 삭제해주는 깨끗하게 삭제해준다고 한다.

#### 2 
수강생 분들 다수가 REPL(Read Eval Print Loop)과 터미널 프롬프트를 잘 구분하지 못하셨다. 예를 들면 REPL에서 `pip install beautifulsoup` 등을 하셨음. 실습 중간에 문제점을 말씀하셔서 실습 속도가 엄청 늦어졌다.

#### 3
수강생 분들 다수가 터미널 자체에 익숙하지 않은 듯 보였다. 대신 주피터 노트북은 익숙하신지 대부분의 개발을 주피터 노트북에서 하시려고 함. 예를 들어 `npm install`을 하시거나..

#### 4 
Python 프로그램 실행하는 방법을 모르시는 분들이 많으셨다. 알려드렸는데 잘 기억하고 계실지 의문.

#### 5 
컴퓨터 내에 디렉토리 관리를 하고 계시는 분이 한 분도 안 계셨다. 그리고 파일 이름을 한글이나 띄어쓰기 등을 넣어 하신 분들도 많았음.


### 2019-10-23 
#### if __name__ == '__main__':의 효과

예를 들어 엑스티가 xt.py 라는 모듈을 만들었는데 이게 import xt 해서 쓰일 수도 있고 python xt.py 해서 쓰일 수도 있다면 이프네임메인 안에 넣은 내용은 python xt.py 했을 때에만 실행되고 import xt 했을 때에는 실행이 안 돼요
파이선에 http.server 라는 모듈이 있어요
https://xtendo.org/ 지금 아데라님이 커맨드라인에다가 python -m http.server 라고 치시면
https://xtendo.org/ 8000번 포트에 웹 서버 하나가 실행되거든요
근데 파이선 인터프리터를 열고 거기서 import http.server 라고 하면
그냥 http.server 모듈이 반입되기만 하고 웹 서버 실행은 안 돼요
즉 "python <모듈명>으로 모듈 지정 실행"했을 때에는 실행되지만, "import로 모듈 반입"했을 때에는 실행되지 않는 코드 <-- 이것을 만들기 위해서 이프네임메인을 쓰는 것이죠
