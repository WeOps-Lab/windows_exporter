## 嘉为蓝鲸Windows Exchange插件使用说明

## 使用说明

### 插件功能

Windows Exchange Exporter用于采集Windows Exchange的指标，通过 Windows Management Instrumentation (WMI) 提供的接口来采集数据。

### 版本支持

操作系统支持: windows

是否支持arm: 否

**组件支持版本：**

可以在支持 WMI 的 Windows 操作系统上采集数据。

**是否支持远程采集:**

否

### 参数说明

Exchange exporter采集目前只可以设置日志级别参数，直接下发到windows服务器即可。

### 使用指引

### 指标简介


| **指标ID**                                                         | **指标中文名**                          | **维度ID**   | **维度含义** | **单位** |
| ------------------------------------------------------------------ | --------------------------------------- | ------------ | ------------ | -------- |
| windows_exchange_up                                                | Exchange插件运行状态                    | -            | -            | -        |
| windows_exchange_rpc_avg_latency_sec                               | Exchange的RPC平均延迟时间               | -            | -            | s        |
| windows_exchange_rpc_requests                                      | Exchange正在处理的客户请求数            | -            | -            | -        |
| windows_exchange_rpc_active_user_count                             | Exchange活跃用户数量                    | -            | -            | -        |
| windows_exchange_rpc_connection_count                              | Exchange客户端连接总数                  | -            | -            | -        |
| windows_exchange_rpc_operations_total                              | Exchange的RPC操作速率                   | -            | -            | -        |
| windows_exchange_rpc_user_count                                    | Exchange用户数量                        | -            | -            | -        |
| windows_exchange_ldap_read_time_sec                                | Exchange LDAP 读取时间                  | service_name | 服务名称     | s        |
| windows_exchange_ldap_search_time_sec                              | Exchange LDAP 搜索时间                  | service_name | 服务名称     | s        |
| windows_exchange_ldap_write_time_sec                               | Exchange LDAP 写入时间                  | service_name | 服务名称     | s        |
| windows_exchange_ldap_timeout_errors_total                         | Exchange LDAP 超时错误总数              | service_name | 服务名称     | -        |
| windows_exchange_ldap_long_running_ops_per_sec                     | Exchange每秒长时间运行的LDAP操作数      | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_external_active_remote_delivery  | Exchange外部活跃远程投递队列长度        | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_internal_active_remote_delivery  | Exchange内部活跃远程投递队列长度        | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_active_mailbox_delivery          | Exchange活跃邮箱投递队列长度            | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_retry_mailbox_delivery           | Exchange重试邮箱投递队列长度            | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_unreachable                      | Exchange不可达队列长度                  | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_external_largest_delivery        | Exchange外部最大投递队列长度            | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_internal_largest_delivery        | Exchange内部最大投递队列长度            | service_name | 服务名称     | -        |
| windows_exchange_transport_queues_poison                           | Exchange中毒物队列长度                  | service_name | 服务名称     | -        |
| windows_exchange_http_proxy_mailbox_server_locator_avg_latency_sec | Exchange邮箱服务器定位器平均延迟时间    | service_name | 服务名称     | s        |
| windows_exchange_http_proxy_avg_auth_latency                       | Exchange平均身份验证延迟时间            | service_name | 服务名称     | s        |
| windows_exchange_http_proxy_outstanding_proxy_requests             | Exchange当前待处理的代理请求数          | service_name | 服务名称     | -        |
| windows_exchange_http_proxy_requests_total                         | Exchange每秒处理的代理请求数            | service_name | 服务名称     | -        |
| windows_exchange_workload_active_tasks                             | Exchange活跃后台任务数                  | service_name | 服务名称     | -        |
| windows_exchange_workload_completed_tasks                          | Exchange已完成后台任务数                | service_name | 服务名称     | -        |
| windows_exchange_workload_queued_tasks                             | Exchange待处理后台任务数                | service_name | 服务名称     | -        |
| windows_exchange_workload_yielded_tasks                            | Exchange已让步任务数                    | service_name | 服务名称     | -        |
| windows_exchange_workload_is_active                                | Exchange负载活跃状态                    | service_name | 服务名称     | -        |
| windows_exchange_activesync_requests_total                         | Exchange每秒处理的 ActiveSync 请求数    | -            | -            | -        |
| windows_exchange_http_proxy_avg_cas_proccessing_latency_sec        | Exchange CAS 处理平均延迟时间           | service_name | 服务名称     | s        |
| windows_exchange_http_proxy_mailbox_proxy_failure_rate             | Exchange邮箱代理失败率                  | service_name | 服务名称     | percent  |
| windows_exchange_activesync_ping_cmds_pending                      | Exchange待处理的Ping命令数              | -            | -            | -        |
| windows_exchange_activesync_sync_cmds_total                        | Exchange每秒处理的同步命令数            | -            | -            | -        |
| windows_exchange_avail_service_requests_per_sec                    | Exchange当前唯一登录用户数              | -            | -            | -        |
| windows_exchange_owa_current_unique_users                          |                                         | -            | -            | -        |
| windows_exchange_owa_requests_total                                | Exchange每秒处理的Outlook Web App请求数 | -            | -            | -        |
| windows_exchange_autodiscover_requests_total                       | Exchange每秒处理的自动发现请求数        | -            | -            | -        |
| windows_exporter_collector_duration_seconds                        | Exchange监控探针采集持续时间            | collector    | 采集目标     | s        |
| windows_exporter_collector_success                                 | Exchange监控探针采集成功状态            | collector    | 采集目标     | -        |

### 版本日志

#### weops_exchange_exporter 2.6.0

- weops调整

添加“小嘉”微信即可获取windows exchange监控指标最佳实践礼包，其他更多问题欢迎咨询

<img src="https://wedoc.canway.net/imgs/img/小嘉.jpg" width="50%" height="50%">
