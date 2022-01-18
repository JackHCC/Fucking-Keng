# Docker



## Install





## Environment

#### *Error: Docker-compose: /usr/local/bin/docker-compose : line 1: Not: command not found*

- **错误原因：** docker-compose官方提供的链接版本号上不能加“v”
- **解决办法：** 
  - 方法一：
    - 将`sudo curl -L "https://github.com/docker/compose/releases/download/v2.1.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`改为：`sudo curl -L "https://github.com/docker/compose/releases/download/2.1.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
    - 注意两个链接2.1.1前面的“v”
- **参考链接：**
  - [链接一](https://stackoverflow.com/questions/58747879/docker-compose-usr-local-bin-docker-compose-line-1-not-command-not-found)
