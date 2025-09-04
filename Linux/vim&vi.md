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