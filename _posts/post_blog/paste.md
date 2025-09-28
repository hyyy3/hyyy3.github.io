

### Linux 

```bash

# cpu 정보 확인
cat /proc/cpuinfo | grep name

# 메모리 용량 확인
cat /proc/meminfo | grep MemTotal

# private ip 주소 확인
ip -br -c addr show eth0

# public ip 주소 확인
curl ipinfo.io/ip

# 스토리지 확인 (EBS 볼륨 확인)
lsblk
df -hT -t xfs


sudo dd if=/dev/zero of=/swapfile bs=128M count=64  # 8GB 스왑 파일 생성
sudo chmod 600 /swapfile                            # root만 접근 가능
sudo mkswap /swapfile                               # 스왑 초기화
sudo swapon /swapfile                               # 스왑 활성화swap 활성화 sudo swapon /swapfile

echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
./gradlew clean build -x test


```





### git

```bash
ntrac
git reset --hard HEAD       # 로컬 변경 사항 초기화
git clean -fd               # uked 파일/디렉토리 삭제
git pull origin main        # 최신 코드 가져오기 (main 브랜치 기준)

git config --global user.name "hyyy3"
git config --global user.email "25hanayuki@gmail.com"
git config --global --list   # 전역 설정 확인
git config --list            # 현재 저장소에서 적용된 설정 확인




## Github blog

```




### EC2

```bash

# 접속 (Ubuntu)
ssh -i "hanay4502-seoul.pem" ubuntu@{ip}


```



``` bash

cd src/main/resources
vim application.properties


sudo systemctl daemon-reload
sudo systemctl restart moneymate
tail -f /home/ubuntu/MoneyMate_BE/app.log
sudo systemctl restart moneymate


cd build/libs
nohup java -jar moneymate-BE-0.0.1-SNAPSHOT.jar > app.log 2>&1 &
tail -f app.log


```





### Jekyll






### MySQL
- mysql 시작 <br> net start mysql, sc.exe start mysql

- mysql 접속 <br> mysql -u root -p  (mysql로 표시됨)

- mysql 서버 실행여부 확인 <br>  sc.exe query mysql

- mysql 종료 <br> 서버 안에서: shutdown;

- 테이블 삭제 <br>
SET FOREIGN_KEY_CHECKS = 0;
TRUNCATE TABLE transaction;
SET FOREIGN_KEY_CHECKS = 1;



- dump (rds) <br>
mysql -h moneymate-db.clceosi6aceb.ap-northeast-2.rds.amazonaws.com -P 3306 -u admin -p test1_bkp

- rds에서 SET SQL_SAFE_UPDATES = 0; 설정: <br>
Workbench 메뉴 → Edit → Preferences → SQL Editor → Safe Updates (rejects UPDATEs and DELETEs with no key in WHERE clause) 체크 해제

```sql



```



## MariaDB
- mariaDB 시작 <br> net start mariaDB, sc.exe start mariadb

- mariaDB 접속 <br> mysql -u root -p  (mysql로 표시됨)

- mariaDB 서버 실행여부 확인 <br>  sc.exe query mariadb  ,          Get-Service mariadb (PS)

- mariaDB 종료 <br> 서버 안에서: shutdown; (가장 안정),  외부에서 프로세스 종료: net stop MySQL  (또는 sc stop MySQL) 

- 3306 포트 열려있는지 확인 <br> netstat -ano | findstr 3306

- 나가기 <br> quit;



"​"너비없는공백 

" " 작은공백 

"⠀" 큰공백




## WSL
```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

dism.exe /online /enable-feature /featurename:VirtualMachinePlatForm /all /norestart

wsl --update
wsl --set-default-version 2

wsl --install Ubuntu-24.04

# 만약 파일 손상으로 타임아웃 발생시 https://github.com/microsoft/WSL/releases 에서 최신 버전 다운받기


# nvm 다운로드 및 설치:  Ubuntu에서 실행해야함
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

# Node.js 다운로드 및 설치:
nvm install 22

# Node.js 버전 확인:
node -v # "v22.20.0"가 출력되어야 합니다.
nvm current # "v22.20.0"가 출력되어야 합니다.

# Verify the Node.js version:
node -v # Should print "v22.20.0".

# npm 버전 확인:
npm -v # 10.9.3가 출력되어야 합니다.




# claude-code 설치
npm install -g @anthropic-ai/claude-code

git clone https://github.com/sysnet4admin/_Book_Claude-Code.git





```







## 환경 변수 설정
```bash
시스템 변수 PATH  JAVA_HOME 이름으로 C:\Program Files\Java\jdk-21

시스템 변수 CLASSPATH 이름으로 %JAVA_HOME%\lib

시스템 변수 Path에 %JAVA_HOME%\bin 추가

```