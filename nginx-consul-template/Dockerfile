FROM nginx:1.15.7-alpine

RUN wget https://releases.hashicorp.com/consul-template/0.19.3/consul-template_0.19.3_linux_amd64.tgz -O /tmp/consul-template.tar.gz
RUN tar -xvzf /tmp/consul-template.tar.gz -C /usr/local/bin

COPY nginx.conf.template /etc/nginx/nginx.conf.template
CMD nginx && nohup consul-template -consul-addr "consul:8500" -template "/etc/nginx/nginx.conf.template:/etc/nginx/nginx.conf:nginx -s reload || true"
