# rust-fullstack-example 

An example of creating a full stack web application (backend and frontend) using Rust.

## Backend

Go to `./backend` and start the server using `make dev`.

## Frontend

Go to `./frontend` and start a local server on port 8080 using `make web`

You can create owners and for each owner, on their detail page, create pets and delete them.

## Prepare

### 安装 PostgreSQL 数据库

0. 安装 PostgreSQL 软件
```
sudo apt install postgresql -y
sudo systemctl enable postgresql
sudo systemctl start postgresql
sudo systemctl status postgresql
sudo netstat -plunt |grep postgres
```
1. 修改 PostgreSQL 数据库默认用户 postgres 的密码
PostgreSQL 数据库创建一个 postgres 用户作为数据库的管理员，密码随机，所以需要修改密码，方式如下：

- 步骤一： 登录 PostgreSQL
```
sudo -u postgres psql
```
- 步骤二： 修改登录 PostgreSQL 密码
```
ALTER USER postgres WITH PASSWORD 'postgres';
```
> 注： 密码 postgres 要用引号引起来, 命令最后有分号.

- 步骤三： 退出 PostgreSQL 客户端
```
\q
```
2. 修改 linux 系统 postgres 用户的密码

PostgreSQL 会创建一个默认的 linux 用户 postgres, 修改该用户密码的方法如下：

- 步骤一： 删除用户 postgres 的密码
```
sudo passwd -d postgres
```
- 步骤二： 设置用户 postgres 的密码
```
sudo -u postgres passwd
```
系统提示输入新的密码
```
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
```

### Project Setup

- Installing Rust​
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
- Install WebAssembly target​
```
rustup target add wasm32-unknown-unknown
```
- Install Trunk​
```
cargo install trunk
```
