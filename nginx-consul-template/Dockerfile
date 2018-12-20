FROM nginx:1.15.7-alpine

COPY consul-template.linux /

COPY nginx.conf.template /etc/nginx/nginx.conf.template
CMD nginx && ./consul-template.linux -consul-addr "consul:8500" -template "/etc/nginx/nginx.conf.template:/etc/nginx/nginx.conf:nginx -s reload || true"
