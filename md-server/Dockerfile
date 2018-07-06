FROM abiosoft/caddy:latest

COPY Caddyfile /etc

RUN mkdir -p /var/www

COPY blog.template.html /var/www

# 這邊直接在建置階段將部落格檔案複製到 image 內指定路徑下
# 也可以考慮使用 Caddy 的 git 插件, 透過 git push 發表部落格
# See https://caddyserver.com/docs/http.git
COPY first-blog.md /var/www
