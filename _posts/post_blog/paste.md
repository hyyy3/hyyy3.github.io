

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

git reset --hard HEAD       # 로컬 변경 사항 초기화
git clean -fd               # untracked 파일/디렉토리 삭제
git pull origin main        # 최신 코드 가져오기 (main 브랜치 기준)


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


- 테이블 삭제 <br>
SET FOREIGN_KEY_CHECKS = 0;
TRUNCATE TABLE transaction;
SET FOREIGN_KEY_CHECKS = 1;



- dump (rds) <br>
mysql -h moneymate-db.clceosi6aceb.ap-northeast-2.rds.amazonaws.com -P 3306 -u admin -p test1_bkp






"​"너비없는공백 

" " 작은공백 

"⠀" 큰공백
