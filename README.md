# tracker2k


A log tracking client integration code for OpenAI agents sdk


### Quick Start

1. 安装client lib sdk

```
pip install tracker2k
```

2. 集成agent服务代码

```
import tracker2k

# 注：
#   1.app_name：指服务的应用名字，例如：xxx-assistant
#   2.env_name：指服务应用的环境名称，例如：dev, pre, prod
#   3.endpoint：指链路远端服务地址
tracker2k.init(app_name="travel-assistant", env_name="dev", endpoint="https://xxx.xxx.xxx/asst/logagent")


# 注：
#   1 trace_id 对应链路的trace_id
#   2. metadata中的query和uid，对应用户请求query和用户id

with trace(
        workflow_name=f"LPY Agent ({session_id})",
        group_id=f'Lpy Agent',
        trace_id=trace_id,
        metadata={"query": query, "uid": uid}
    ):
    ...your code...
```

3. 查看追踪数据

可以仿照OpenAI platform traces的界面，实现自己的前端展示效果

