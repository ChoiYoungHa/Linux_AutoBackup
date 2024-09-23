# <p align="center">[🐠 Linux 백업 시스템 구축 미니프로젝트] 

<br>

# 🙆‍♀️ 프로젝트 개요
> Crontab과 Shell Script를 사용하여 로그 및 데이터베이스 덤프파일 등 시스템에서 중요한 파일을 매일 9시에 백업하도록 한다.<br>
> 리눅스의 다양한 명령어와 시스템 관리 방법을 배울 수 있으며 tar, rsync, cron, find 등 시스템 백업 및 파일 관리를 위한 유용한 명령어들을 익힐 수 있다.

<br>

# 🚢 학습 목적
- Linux에서 Crontab 활용하기
- Shell Script 작성하여 반복작업 자동화하기
<br>


<br>

# 🚨 실행 순서
### 🍦ShellScript 작성

```shell
#!/bin/bash

today=$(date +%Y%m%d)

backup_dir="/home/username/backup"
mkdir -p "$backup_dir"

# tar 명령어로 백업 생성
tar zcfp "$backup_dir/backup-$today.tar.gz" /home/username/step02shell

# 5일이 지난 백업 파일 삭제
find "$backup_dir" -type f -mtime +5 -exec rm -f {} \;
```

### 🥯Crontab 등록
```shell
crontab -e
0 09 * * * /home/username/script/cronshell.sh
```

### 🥝결과
![2024-09-23 18 19 42](https://github.com/user-attachments/assets/23a437da-f70c-46d9-9e10-4f8a8c4b1fe6)
