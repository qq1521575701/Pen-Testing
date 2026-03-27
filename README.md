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
    
## 
