# Pen-Testing

# 子域名爆破

## 拉取镜像
    docker pull blechschmidt/massdns
## dns扫描
    docker run --rm -v $(pwd):/data projectdiscovery/dnsx \
    -d 19981026.xyz \
    -w /data/子域名字典.txt \
    -t 3000 \
    -o /data/result.txt \
    -r 1.1.1.1
    
