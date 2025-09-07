## vi 사용법

#### 입력 모드 전환 명령 키

- i : 커서 앞에 입력(현재 커서 자리에 입력)
- a : 커서 뒤에 입력(현재 커서 다음 자리에 입력)
- o : 커서가 위치한 행의 다음 행에 입력
- I : 커서가 위치한 행의 첫 칼럼으로 이동하여 입력
- A : 커서가 위치한 행의 마지막 칼럼으로 이동하여 입력
- O : 커서가 위치한 행의 앞 행에 입력

#### 파일 저장 및 종료 키

* Last-line mode
- :q : quit when there was no work you have done
- :q! : quit without saving your work
- :w[file name] : only saving your work. if you designated the file name, it will be saved as a new file name
- :wq, :wq! : saving your work and quit the vi

* Command mode
(Shift+zz) ZZ : quit vi after saving your work

#### 커서 이동 명령 키

- k : move the cursor up one line
- j : move the cursor down one line
- l : move the cursor one character to the right
- h : move the cursor one character to the left
- ^

### vim 사용법

a : 커서 위치 다음칸부터 입력
A : 커서 행의 맨 마지막부터 입력
i : 커서의 위치에 입력
I : 커서 행의 맨 앞에서 부터 입력
o : 커서의 다음행에 입력
O : 커서의 이전 행에 입력
s : 커서 위치의 한글자를 지우고 입력
cc : 커서 위치의 한 행을 지우고 입력

b : 한 단어 뒤로 이동 (back) 
w : 한 단어 앞으로 이동 (forward) 
H : 화면 맨 위로 이동 
M : 화면 중간으로 이동 
L = G : 화면 맨 아래로 이동 
nG : n번째 줄로 이동 

* 복사 (yank) 
yy  : 한줄 복사
yyn : n줄 만큼 복사 (똑같은걸 n줄 복사)  
yw  : 한 단어 복사 (yank word) 
ynw : n 단어 복사 (똑같은 단어를 n번 복사) 
y$  : 커서부터 이줄 끝까지 복사 
y0  : 커서부터 이줄 앞까지 복사

* 붙여넣기 
p : 커서 앞으로 붙여넣기
P : 커서 뒤로 붙여넣기 

* 삭제 (delete) 
x : 커서 뒤의 문자 하나 삭제
X : 커서 앞에 문자 하나 삭제 
dd : 한줄 삭제
ddn : n줄 삭제 
dw : 한 단어 삭제 (delete word) 
dnw : n 단어 삭제 
d$ : 커서부터 이줄 끝까지 삭제
d0 : 커서부터 이줄 앞까지 삭제 
dG : 커서부터 문서 끝까지 삭제  

* 명령 되돌리기 
u : 되돌리기 (undo) 

* 검색 
/검색할 단어

출처: https://sseozytank.tistory.com/77