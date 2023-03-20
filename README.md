# Quick Start 


### 修改数据库连接配置
```
DATABASES = {
'default': {
    'NAME': 'news',  # 数据库名
    'ENGINE': 'django.db.backends.mysql',
    'USER': 'root',  # 用户名
    'PASSWORD': '123456',  # 密码
    'HOST': '192.168.0.107',  # 替换本机的IP
    'PORT': '3306',  # 端口
    'useSSL': 'false',
  }
}


### 启动服务

```sh
docker-compose build
docker-compose up -d
```

### 导入数据

1. 打开网页: http://0.0.0.0:8081/ 
2. 输入用户名root ， 密码123456
3. 在左侧sql命令中，把news.sql的内容复制进去，执行

#### 创建登陆用户

1. 打开swagger网页: http://0.0.0.0:8000/
2. 找到`Post /user/ 用户查询和注册的` 接口
3. 右侧点击`Try it out`, 并输入username，password

#### 修改用户为超级管理员
1. 进入数据库:  http://0.0.0.0:8081/ 
2. 输入用户名root ， 密码123456, 数据库 news
3. 找到`auth_user`表，点击`选择数据`
4. 通过 username 找到刚才注册的账号
5. 点击左侧的编辑，修改 `is_superuser`和`is_staff` 为1

#### 浏览网页
1. 打开网页: http://0.0.0.0:8000/admin/
2. 输入刚才注册的账号密码