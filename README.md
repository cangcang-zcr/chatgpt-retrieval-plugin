项目在本地运行Redis数据库，将数据切块并使用chatgpt embeding api 存入数据库
查询时检索相近数据


```
git clone git@github.com:cangcang-zcr/chatgpt-retrieval-plugin.git
```
 
 进入本项目目录后
```
cd examples/docker/redis/
```

启动docker 容器中的redis
```
docker compose up -d
```

回到前一个目录
```
cd -
```

初始化系统参数，本地测试不使用bear 验证，所以无需配置bear token
项目测试使用redis
```
export DATASTORE=redis
export OPENAI_API_KEY=<your_openai_api_key>
```

需要预先安装python3.10

安装poetry
```
pip install poetry

```
创建一个虚拟环境
```
poetry env use python3.10
```
安装依赖
```
poetry install
```

启动项目
```
poetry run start
```
见到启动完成
```
INFO:     Uvicorn running on http://0.0.0.0:8000
INFO:     Application startup complete.
```

另一终端
启动juypter notebook服务
```
pip install juypter notebook
juypter notebook
```

启动后运行 ./local.ipynb 文件代码
