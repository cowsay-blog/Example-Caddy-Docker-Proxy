# Example: Caddy Docker Proxy
在 Docker swamp 中使用 Caddy 做反向代理｡

## 啟動服務
1. 在呼叫 `docker stack deploy` 之前, 需要先用 swarm 指令進行初始化｡
(參考[官方文件說明](https://docs.docker.com/get-started/part3/#run-your-new-load-balanced-app))
```
docker swarm init
```

2. 接著啟動所有服務, `example-caddy-docker-proxy` 是我給這個叢集的名稱｡
```
docker stack deploy -c docker-compose.yml example-caddy-docker-proxy
```

3. 使用瀏覽器連線到 http://whoami.cowsay.blog 和 http://cowsay.blog 測試效果｡