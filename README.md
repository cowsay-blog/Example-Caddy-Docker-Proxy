# Example: Caddy Docker Proxy
在 Docker swamp 中使用 Caddy 做反向代理｡

## 啟動服務
1. 在呼叫 `docker stack deploy` 之前, 需要先用 swarm 指令進行初始化｡
(參考[官方文件說明](https://docs.docker.com/get-started/part3/#run-your-new-load-balanced-app))
```
docker swarm init
```

2. 建置所有自訂的 image (範例中的 md-server 這個 image)
```
docker-compose build
```

3. 接著啟動所有服務, `example-caddy-docker-proxy` 是我給這個叢集的名稱｡
```
docker stack deploy -c docker-compose.yml example-caddy-docker-proxy
```

4. 使用瀏覽器連線到 http://whoami.cowsay.blog 和 http://cowsay.blog/first-blog 測試效果｡

5. 停止所有服務
```
docker stack rm example-caddy-docker-proxy
```

## 注意!
http://whoami.cowsay.blog 和 http://cowsay.blog 這兩個網址為**牛牛**所擁有, 在我關閉這兩個服務之前都可以連線過去看看這個範例的效果｡

如果你需要自己嘗試, 請將 [docker-compose.yml](./docker-compose.yml) 中的 whoami 和 md-server 這兩個服務的 `caddy.address` 改為屬於你的網域｡