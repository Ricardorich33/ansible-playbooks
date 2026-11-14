# ansible-playbooks

常用 Ansible Playbook 集合，用于 Linux 主机初始化、Nginx 安装、Docker 安装等。

## 目录

- `inventory/hosts.ini`：主机清单示例
- `group_vars/all.yml`：公共变量
- `playbooks/common.yml`：系统初始化（时区、chrony、基础包、普通用户、SSH 加固）
- `playbooks/nginx.yml`：安装并启动 Nginx
- `playbooks/docker.yml`：安装 Docker 与 compose 插件

## 使用

1. 修改 `inventory/hosts.ini`，把目标主机 IP 和 SSH 信息换成你的环境。
2. 测试连通性：`ansible all -m ping`
3. 执行：`ansible-playbook -i inventory/hosts.ini playbooks/common.yml`

## 注意事项

- 示例以 CentOS/RHEL 为主，Debian/Ubuntu 需要调整包名。
- 生产环境建议用 SSH key 登录，不要把密码明文写进清单文件。
