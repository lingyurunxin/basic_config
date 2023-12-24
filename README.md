proxy-groups:
  - name: 国内网站
    type: select
    proxies:
      - DIRECT
  - name: 科学上网
    type: select
    proxies:
      - 科学服务器

rule-providers:
  foreign_url:
    type: http
    behavior: domain
    format: text
    path: ./ruleset/foreign_url.txt
    url: https://raw.githubusercontent.com/lingyurunxin/basic_config/main/foreign_url.txt

rules:
  - RULE-SET,foreign_url,科学上网
  - DOMAIN-SUFFIX,github.com,科学上网
  - MATCH,国内网站
