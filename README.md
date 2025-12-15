# 오픈소스 소프트웨어 이해와 실습 과제

> 2025047026 김민중

---

# 🛠️ Mini CLI Tool Project

> 간단한 CLI 프로그램을 제작하고, Linux 실행 및 Docker 패키징, GitHub 버전관리 실습을 수행한 프로젝트입니다.

---

## 📁 프로젝트 구조

```
mini-cli/
 ├─ src/
 │   └─ mini.c
 ├─ Dockerfile
 ├─ README.md
 ├─ LICENSE
 └─ docs/
     └─ images/
```

---

## 🚀 1. Mini 프로그램

### ✔ 코드


```c
#include <stdio.h>
int main() {
    for (int i = 0;i < 5;i++) {
        printf("Hello from Mini C Program!\n");
    }
    printf("name : 김민중\n");
    printf("student number : 2025047026\n");
    return 0;
}
```

---

## 🧪 2. Linux 실행 결과

### ✔ 실행 명령어
```bash
# 개발 환경 설치 과정
sudo apt update
sudo apt install -y build-essential
# 실행 과정
gcc src/mini.c -o mini
./mini
Hello from mini C Program!
Hello from mini C Program!
Hello from mini C Program!
Hello from mini C Program!
Hello from mini C Program!
name : 김민중
student number : 2025047026
```

### 실행 화면 캡처  
![Linux 실행 화면](docs/images/linux-run.png)

---

## 3. Dockerfile 및 실행 결과

### ✔ Dockerfile
```Dockerfile
FROM ubuntu:24.04
WORKDIR /app
COPY src/mini.c .
RUN apt update && \
    apt install -y gcc && \
    gcc mini.c -o mini
CMD ["./mini"]
```

> 작성 요령: 이미지 빌드 과정 및 이미지 실행 과정 작성(화면 캡쳐) <- 작성 완료 후 삭제

### ✔ Docker 이미지 빌드
```bash
docker build -t mini-cli .
```

### ✔ Docker 실행
```bash
docker run --rm mini-cli
```

### ✔ 실행 화면 캡처  
(예: `docs/images/docker-run.png`)

---

## 4. GitHub 버전관리 내역

> 작성 요령: 의미 있는 커밋 메시지 및 브랜치 사용 <- 작성 완료 후 삭제

### 체크리스트
- [ ] Commit 5회 이상  
- [ ] Branch 생성  
- [ ] Branch → main Merge  
- [ ] 의미 있는 Commit 메시지  

### 설명
예)
```
feature/output-update 브랜치를 생성해 기능을 수정하고 main으로 merge함.
```

### 캡처
(예: `docs/images/git-log.png`)

---

## 5. LICENSE 파일  
선택한 라이선스: MIT / Apache-2.0 / Unlicense 등

```
본 프로젝트는 {설정한 라이센트 작성} License를 적용합니다.
```

---

## 6. 고찰

> 작성 요령: 아래의 내용을 자유롭게 작성 <- 작성 완료 후 삭제

- 배운 점:  
- 어려웠던 점:  
- 흥미로웠던 부분:  
- 개선하고 싶은 점:  

---

## 7. 참고 자료

> 작성 요령: 과젱에 참고한 레퍼런스가 있다면 작성(아래는 예시) <- 작성 완료 후 삭제

- https://docs.docker.com/  
- https://gcc.gnu.org/  
- https://choosealicense.com/
