# Pen-Testing

    cd /root && rm -rf Pen-Testing && git clone https://github.com/qq1521575701/Pen-Testing.git && cd Pen-Testing

# 子域名爆破

## 拉取镜像
    docker pull blechschmidt/massdns
## dns扫描
    docker run --rm -v $(pwd):/data projectdiscovery/dnsx -d host -w /data/子域名字典.txt -t 3000 -o /data/result.txt -r 1.1.1.1
    
# 站点是否存在查询

## 拉取镜像
    docker pull projectdiscovery/httpx
## 站点扫描
    docker run --rm -v $(pwd):/data projectdiscovery/httpx -l /data/result.txt silent -o /data/http_alive.txt 

# 目录扫描

## 下载
    apt update && apt install ffuf -y
    
## 目录扫描
    ffuf -w 目录字典/admin.txt -u host/FUZZ

# SQL注入

## 安装
    cd /root && rm -rf sqlmap && git clone https://github.com/sqlmapproject/sqlmap.git && cd sqlmap && touch sql.txt

## 注入测试
    python3 sqlmap.py -r sql.txt --batch

## 用户名爆破
    ffuf -request req.txt -w 用户名字典.txt -mr '密码错误' -t 800
## 账号密码爆破
    ffuf -request req.txt -w username.txt:USERNAME -w password.txt:PASSWORD -mr '200' -t 800
