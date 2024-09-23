# <p align="center">[🚂 Linux Shell Script, Crontab를 활용한 백업 시스템 구축 프로젝트] 

<br>

# 🙆‍♀️ 프로젝트 개요
Crontab과 Shell Script를 사용하여 로그 및 데이터베이스 덤프파일 등 시스템에서 중요한 파일을 매일 9시에 백업하도록 한다.<br>

1. Shell Script를 작성한다.
2. Crontab에 스크립트를 등록한다.

<br>

# 🚢 학습 목적
- Linux에서 Crontab 활용하기
- Shell Script 작성하여 반복작업 자동화하기
<br>


<br>

# 🚨 실행 순서
### 🍦 1.Shell Script 작성
```shell
#!/bin/bash

today=$(date +%Y%m%d)

backup_dir="/home/username/backup"
mkdir -p "$backup_dir"

# tar 명령어로 백업 생성 (fisa 권한 유지 옵션 포함)
tar zcfp "$backup_dir/backup-$today.tar.gz" /home/username/step02shell

# 5일이 지난 백업 파일 삭제
find "$backup_dir" -type f -mtime +5 -exec rm -f {} \;
```

### 🥯 2.Crontab 등록


# 결론 및 고찰
