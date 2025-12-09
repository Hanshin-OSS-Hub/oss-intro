

# 기말시험: **오픈소스SW개론 (SH207)**

+ **시험 일시:** 2025.12.9 (화) 09:30 - 10:45
+ **시험 방식:** Git 실습
+ **제출 방식:** Git Bash(또는 터미널)의 전체 실행 출력 내용을 복사하여 텍스트 파일(`final-exam-<학번>.txt`)로 저장 → LMS 과제 게시판에 제출

## 부록. 주요 Git 명령어 목록

<span style="color:#002060">**명령어**</span> (<span style="color:blue">옵션1</span> | <span style="color:blue">옵션2</span> | <span style="color:blue">...</span>) <<span style="color:#00aa00">인자</span>>


### 📌 Git 명령어

```
git add <file_name>
git branch (-d) <branch_name>
git checkout (-b) <branch_name>
git clone <repository_url>
git commit ( -m | -am ) "<message>"
git config ( --global | --list | --system | --unset )
git credential-manager (--version)
git diff (--cached) <commit_ID_original> <commit_ID_latest>
git diff (--cached) <branch_name_one> <branch_name_two>
git init
git log ( --oneline | --graph | --all | -p | --stat | --author="<author_name>" | --since="<date>") <branch_name>
git merge <branch_name> (-m) "<message>"
git push <remote_name> <branch_name>
git rebase <branch_name>
git remote (-v)
git remote add <alias> <repository_url>
git reset (--hard) <commit_ID>
git reset (--hard) <relative_ref>
git revert <commit_ID>
git reset <relative_ref>
git rm (--cached) <file_name>
git rm (--cached) <directory_name>
git status
```

### 📌 쉘 명령어
```
cat <file_name>
cd ( / | ~ | .. | - | <directory_name> )
cp <source_file_path> <destinaiton_directory> 
echo "<message>" ( > | >> ) <file_name>
ls ( -l | -a | -la ) <directory_name>
mkdir <directory_name>
mv <file_name_from> <file_name_to>
pwd
rm <file_name>
```

### 📌 문서 편집기
```vim <file_name>``` : 파일 열기
+ `dd` 입력 : 현재 위치의 코드 한 줄을 삭제
+ 저장 및 종료: `ESC` 키 ⇨ `:` 키 ⇨ `wq` 입력 ⇨ `Enter` 키

```nano <file_name>``` : 파일 열기
+ `CTRL`+`s` : 파일 저장
+ `CTRL`+`x` : 종료

### 📌 상대참조(relative ref)
```
HEAD
HEAD~<n>
HEAD^
HEAD^^
```

### 📌 .gitignore 파일 작성 문법
```
<directory_name>
*.<file_extension>
!<file_name>
```

## 📘 문제 1. Git 저장소 초기화

다음 단계에 따라 **디렉터리를 생성하고 Git 저장소를 초기화하세요**.

### **[1] 작업 디렉토리 생성 및 이동**

1. 현재 작업 디렉토리 경로를 출력 및 확인하세요.

2. ```final-exam``` 디렉토리를 생성하세요.

3. 생성된 디렉토리로 이동하세요.

4. 현재 디렉토리의 파일 목록을 출력하세요.

---

### **[2] Git 저장소 초기화 확인**

1. ```final-exam``` 디렉토리에서 저장소를 초기화하세요.

2. 숨김 파일을 포함하여 파일 목록을 출력하세요.
   
+ `.git` 디렉토리가 화면에 출력되어야 합니다.

---

### **[3] Git 사용자 정보 설정 및 확인**

1. 다음의 값으로 Git 사용자 정보를 설정하세요.
* `user.name`: `"FinalExamUser"`
* `user.email`: `exam@example.com`

2. Git 설정 정보를 출력하여 `user.name`, `user.email` 가 올바르게 설정되었는지 확인하세요.

---

### **[4] 초기 저장소 상태 확인**

1. 저장소 상태를 출력 및 확인하세요.

---

## 📘 문제 2. Git 스테이징·커밋·파일 수정

다음 단계에 따라 **Git 저장소에서 파일을 생성 및 수정**하는 과정을 수행하세요.

### **[1] 텍스트 파일 생성 및 내용 확인**

1. 다음 내용을 포함하는 `log.txt` 파일 생성하세요.

   ```
   This is the first line of the log.
   ```
2. 파일의 내용을 출력하세요.

3. 저장소 상태를 출력 및 확인하세요.
---

### **[2] 파일 스테이징 및 첫 커밋**

1. 생성된 파일(`log.txt`)을 스테이징하세요.

2. 저장소 상태를 출력 및 확인하세요.

3. 아래 메시지로 커밋하세요.

   ```
   Add initial log file.
   ```

4. 커밋 이후 저장소 상태를 다시 출력 및 확인하세요.
---

### **[3] 파일 수정 및 변경 확인**

1. `log.txt` 파일 마지막에 다음 텍스트를 추가하세요.

   ```
   Second line: updating the log.
   ```
2. 파일을 출력하여 내용이 추가되었는지 확인하세요.
   
3. 현재 저장소 상태를 출력 및 확인하세요.

---

### **[4] 스테이징 및 커밋**
1. 수정된 파일을 스테이징하세요.

2. 아래 메시지로 커밋하세요.

   ```
   Append second line to log.
   ```

---

### **[5] 변경 내용 비교**

1. 커밋 히스토리를 출력하세요.

2. 특정 명령어를 이용하여 가장 최근 커밋과 그 이전 커밋의 차이를 출력 및 비교하세요.

---


## 📘 문제 3. 병합 충돌 해결

다음 단계에 따라 Git 저장소에서 병합 충돌을 **직접 생성하고 해결하세요**.

### **[1] 기본 브랜치 준비**

1. `master` 브랜치에서 `notes.txt` 파일을 생성하고 다음 내용 한 줄을 추가하세요.

   ```
   This line was added in master.
   ```
2. `notes.txt` 파일을 스테이징하고 커밋하세요.

---

### **[2] test 브랜치 생성 및 수정**

1. `test` 브랜치를 생성하고 해당 브랜치로 변경하세요.

2. 같은 파일(`notes.txt`)에 아래 내용을 **파일 마지막 줄**에 추가하세요.

   ```
   This line was added in test.
   ```
3. 파일을 스테이징하고 커밋하세요.

---

### **[3] master 브랜치에서 다른 내용 수정**

1. 다시 `master` 브랜치로 이동하세요.
2. `notes.txt`에 아래 내용을 **똑같이 파일 마지막 줄**에 추가하세요.

   ```
   This line was added by master at the same location.
   ```
3. 파일을 스테이징하고 커밋하세요.

---

### **[4] 병합 충돌 발생시키기**

1. `master` 브랜치에서 `test` 브랜치 병합을 시도하세요.

+ 그 결과, 병합 충돌이 발생했다는 메시지가 출력되어야 합니다.
---

### **[5] 충돌 해결하기**

1. `notes.txt` 파일에는 다음의 충돌 표시가 있어야 합니다:

   ```
   <<<<<<< HEAD
   This line was added by master at the same location.
   =======
   This line was added in test.
   >>>>>>> test
   ```

2. 충돌 표시를 제거하고 **아래와 같이 master의 내용을 유지하는 방식으로** 수동 해결하세요.

   ```
   This line was added in master.
   This line was added by master at the same location.
   ```

3. 스테이징&커밋을 수행하세요.

---

### **[6] 결과 확인**

1. 병합 커밋이 생성되었는지 커밋 히스토리를 확인하세요.

---

## 📘 문제 4. 이전 커밋으로 되돌아가기

다음 단계에 따라 파일을 한 줄씩 추가하는 **세 개의 커밋을 연속으로 수행한 뒤 이전 커밋으로 복구하세요.**

### **[1] 첫 번째 파일 생성 및 커밋**

1. 아래 내용을 포함한 파일 `history.txt`을 생성하세요.

   ```
   Version 1: Initial content.
   ```

2. 파일 내용을 출력 및 확인하세요.

3. 파일을 스테이징하고 다음의 메시지로 커밋하세요.

    ```
    Add version 1 of history file
    ```
   
---

### **[2] 두 번째 수정 및 커밋**

1. 아래 내용을 파일 `history.txt` 끝에 추가하세요.

   ```
   Version 2: Added second update.
   ```

2. 파일 내용을 출력 및 확인하세요.

3. 두 번째 변경을 스테이징하고 및 다음의 메시지로 커밋하세요.

   ```
   Add version 2 update
   ```

---

### **[3] 세 번째 수정 및 커밋**

1. 아래 내용을 파일 `history.txt` 끝에 추가하세요.

   ```
   Version 3: Added third update.
   ```

2. 파일 내용을 출력 및 확인하세요.

3. 세 번째 변경을 스테이징하고 및 다음의 메시지로 커밋하세요.

   ```
   Add version 3 update
   ```

4. 커밋 히스토리를 한 줄 형식으로 출력하세요.

---

### **[4] 변경사항 취소하기**

1. **[복합 수행]** 다음의 요구사항을 만족하면서 직전 두 개의 커밋에 대한 변경사항들을 취소하는 명령어들을 수행하세요.

+ `history.txt` 의 현재 상태

    ```
    Version 1: Initial content.
    Version 2: Added second update.
    Version 3: Added third update.
    ```

+ `history.txt` 내용이 다음과 같도록 이전 커밋 상태로 되돌아가세요.
  
    ```
    Version 1: Initial content.
    ```

+ 요구사항: **편집기에서 내용을 직접 삭제하는 방식은 안되며, 어떠한 커밋 히스토리 삭제도 허용되지 않음**
+ Tip: 커밋 취소 후에 자동으로 편집기가 실행되면 `:wq` 입력하여 종료하세요.
+ Tip: 커밋을 연속으로 두 개를 취소하는 문제이며, **한 개 취소한 뒤 커밋 히스토리를 확인하여 다음에 취소할 커밋의 ID 또는 상대참조 내용을 확인**하는 것을 권장합니다.

2. 파일 내용을 출력하여 Version 2,3가 제거되었는지 확인하세요.

3. 커밋 히스토리를 한 줄 형식으로 출력하세요.

---

## 📘 문제 5. 히스토리 정리하기

**브랜치에서 여러 개의 커밋을 만든 뒤, 특정 명령어를 활용해 히스토리를 정리**하세요.

---

### **[1] 초기 저장소 준비**

1. 다음의 내용을 포함하는 'story.txt' 파일을 생성하세요.
   ```
   Base version
   ```

2. 스테이징 및 커밋하세요.

---

### **[2] 새 브랜치 생성 및 여러 개의 커밋 만들기**

1. 새로운 브랜치 `feature` 생성 및 변경하세요.

2. 파일 수정 1: 다음 메시지를 `story.txt` 끝에 추가한 뒤 스테이징&커밋하세요.

   ```
   Feature update 1
   ```

3. 파일 수정 2: 다음 메시지를 `story.txt` 끝에 추가한 뒤 스테이징&커밋하세요.

   ```
   Feature update 2
   ```

4. 파일 수정 3: 다음 메시지를 `story.txt` 끝에 추가한 뒤 스테이징&커밋하세요.

   ```
   Feature update 3
   ```

5. `feature` 브랜치의 커밋 히스토리를 한 줄로 출력 및 확인하세요.

---

### **[3] master 브랜치 수정**

1. `master` 브랜치로 변경하세요.

2. `story.txt` 파일을 복사해서 `story_copy.txt` 을 생성하세요.

3. 스테이징&커밋하세요.

4. 전체 커밋 히스토리를 한 줄 형태의 그래프로 출력하세요.

### **[4] 히스토리 정리**

1. **[복합수행]** `master` 브랜치의 최신 상태 위로 feature 브랜치를 리베이스하세요.
+ 어떤 브랜치에서 리베이스해야 하는지 잘 생각하세요.

2. 전체 커밋 히스토리를 한 줄 형태의 그래프로 출력하세요.

3. **[복합수행]** `master` 브랜치를 `feature` 브랜치와 같은 버전이 되도록 리베이스하세요.

4. 전체 커밋 히스토리를 한 줄 형태의 그래프로 출력하세요.
+ 최신 커밋 메시지가 다음과 같아야 합니다(`HEAD`가 `master`와 `feature` 모두를 가리키는 상태).
  
    ```
    * <commit_ID> (HEAD -> master, feature) <commit_message>
    ```
---

### 시험이 종료되었습니다. 수고 많으셨습니다. 😊
