## 嘉为蓝鲸IIS插件使用说明

## 使用说明

### 插件功能  
IIS Exporter用于采集Internet Information Services（IIS）服务器的性能指标。它通过从Perflib（Performance Library）获取监控数据来实现监控功能。

### 版本支持

操作系统支持: windows

是否支持arm: 否

**组件支持版本：**

IIS Exporter 支持的 IIS 版本为 7.0 及以上。

**注意** 
部分指标需要 IIS 8 及以上版本才能够正确采集。 例如: windows_iis_worker_request_errors_total、windows_iis_worker_current_websocket_requests  
建议使用 IIS 10.0 或更高版本作为采集对象，以确保能够获得更完整的性能指标数据。

**是否支持远程采集:**

否

### 参数说明
IIS exporter采集目前只可以设置日志级别参数，直接下发到windows服务器即可。

### 使用指引
1. 检查 IIS 服务是否已启动：  
- 打开 IIS 管理器： 
   - 直接进入 IIS 管理器： 
       在计算机中搜索并运行 "IIS 管理器"。选择你的服务器，然后在左侧面板中展开 "服务器名"，选择 "应用程序池"，在右侧窗口中查看应用程序池的状态。  
   - 使用服务器管理器进入 IIS 管理器：  
       使用开始菜单或搜索栏找到 "服务器管理器" 并打开。打开 "服务器管理器"，在左侧面板中选择 "IIS"。右键点击你的服务器，选择 "Internet Information Services (IIS) 管理器"。  
    
- 检查应用程序池和网站状态：  
    在 IIS 管理器中，展开 "服务器名"，然后选择 "应用程序池"。在应用程序池窗口内查看应用程序池的状态。同时，选择 "网站"，然后右键点击网站，在管理网站选项中查看是否已启动。 

- 验证 IIS 服务是否启动： 
    在浏览器中输入默认的 IIS 服务地址：http://127.0.0.1。如果 IIS 服务已启动并运行，你应该会看到 "Internet Information Services" 或类似的内容页面。否则，可能会显示连接错误或无法访问页面。  

2.  检查性能计数器
- `Get-Counter '\Web Service(_total)\*'` 此命令将返回有关IIS Web服务的总体性能计数器信息。

### 指标简介
| **指标ID**                                            | **指标中文名**                   | **维度ID**              | **维度含义**        | **单位** |
|-----------------------------------------------------|-----------------------------|-----------------------|-----------------|--------|
| windows_iis_service_uptime                          | IIS服务的运行时间                  | site                  | 站点              | s      |
| windows_iis_current_anonymous_users                 | IIS当前匿名用户数                  | site                  | 站点              | -      |
| windows_iis_current_blocked_async_io_requests       | IIS当前阻塞的异步I/O请求数            | site                  | 站点              | -      |
| windows_iis_current_cgi_requests                    | IIS当前处理中的CGI请求数             | site                  | 站点              | -      |
| windows_iis_current_connections                     | IIS当前活动连接数                  | site                  | 站点              | -      |
| windows_iis_current_isapi_extension_requests        | IIS当前处理中的ISAPI扩展请求数         | site                  | 站点              | -      |
| windows_iis_current_non_anonymous_users             | IIS当前非匿名用户数                 | site                  | 站点              | -      |
| windows_iis_received_bytes_total                    | IIS启动后接收到的总字节数              | site                  | 站点              | bytes  |
| windows_iis_sent_bytes_total                        | IIS启动后发送的总字节数               | site                  | 站点              | bytes  |
| windows_iis_anonymous_users_total                   | IIS启动后建立的匿名用户数              | site                  | 站点              | -      |
| windows_iis_connection_attempts_all_instances_total | IIS启动后尝试的连接总数               | site                  | 站点              | -      |
| windows_iis_requests_total                          | IIS启动后的请求总数                 | site, method          | 站点, 请求方法        | -      |
| windows_iis_files_received_total                    | IIS接收的文件总数                  | site                  | 站点              | -      |
| windows_iis_files_sent_total                        | IIS发送的文件总数                  | site                  | 站点              | -      |
| windows_iis_locked_errors_total                     | IIS锁定错误总数                   | site                  | 站点              | -      |
| windows_iis_non_anonymous_users_total               | IIS非匿名用户总数                  | site                  | 站点              | -      |
| windows_iis_rejected_async_io_requests_total        | IIS拒绝的异步 I/O 请求总数           | site                  | 站点              | -      |
| windows_iis_current_application_pool_state          | IIS当前应用程序池状态                | app, state            | 应用程序, 状态        | -      |
| windows_iis_current_worker_processes                | IIS当前运行的 worker 进程数         | app                   | 应用程序            | -      |
| windows_iis_maximum_worker_processes                | IIS最大创建的 worker 进程数         | app                   | 应用程序            | -      |
| windows_iis_recent_worker_process_failures          | IIS在快速故障保护间隔内worker进程失败的次数  | app                   | 应用程序            | -      |
| windows_iis_total_application_pool_recycles         | IIS应用程序池的回收总数               | app                   | 应用程序            | -      |
| windows_iis_total_worker_process_failures           | IIS worker 进程崩溃总数           | app                   | 应用程序            | -      |
| windows_iis_total_worker_process_ping_failures      | IIS未收到 worker 进程的 ping 响应总数 | app                   | 应用程序            | -      |
| windows_iis_worker_request_errors_total             | IIS工作进程的请求错误总数              | app, pid, status_code | 应用程序, 进程ID, 状态码 | -      |
| windows_iis_worker_current_websocket_requests       | IIS工作进程正在处理的WebSocket连接数    | app, pid              | 应用程序, 进程ID      | -      |
| windows_iis_server_file_cache_memory_bytes          | IIS服务器文件缓存当前使用的字节数          | -                     | -               | bytes  |
| windows_iis_server_file_cache_max_memory_bytes      | IIS服务器文件缓存使用的最大字节数          | -                     | -               | bytes  |
| windows_iis_server_file_cache_queries_total         | IIS服务器文件缓存查询总数              | -                     | -               | -      |
| windows_iis_server_file_cache_hits_total            | IIS服务器文件缓存的成功查找总数           | -                     | -               | -      |
| windows_iis_server_file_cache_items                 | IIS服务器当前缓存中存在内容的文件数         | -                     | -               | -      |
| windows_iis_server_uri_cache_hits_total             | IIS服务器URI缓存的成功查找总数          | mode                  | 模式              | -      |
| windows_iis_server_uri_cache_items                  | IIS服务器当前缓存中存在的URI信息块数       | mode                  | 模式              | -      |
| windows_iis_server_metadata_cache_items             | IIS服务器当前缓存中存在的元数据信息块数       | -                     | -               | -      |
| windows_iis_server_metadata_cache_queries_total     | IIS服务器元数据缓存查询总数             | -                     | -               | -      |
| windows_iis_server_metadata_cache_hits_total        | IIS服务器元数据缓存的成功查找总数          | -                     | -               | -      |
| windows_iis_server_output_cache_items               | IIS服务器输出缓存中当前存在的项数          | -                     | -               | -      |
| windows_iis_server_output_cache_memory_bytes        | IIS服务器输出缓存当前使用的字节数          | -                     | -               | bytes  |
| windows_iis_server_output_cache_hits_total          | IIS服务器输出缓存的成功查找总数           | -                     | -               | -      |
| process_cpu_seconds_total                           | IIS探针进程CPU秒数总计              | -                     | -               | s      |
| process_max_fds                                     | IIS探针进程最大文件描述符数             | -                     | -               | -      |
| process_open_fds                                    | IIS探针进程打开文件描述符数             | -                     | -               | -      |
| process_resident_memory_bytes                       | IIS探针进程常驻内存大小               | -                     | -               | bytes  |
| process_virtual_memory_bytes                        | IIS探针进程虚拟内存大小               | -                     | -               | bytes  |


### 版本日志

#### weops_IIS_exporter 2.6.0

- weops调整

添加“小嘉”微信即可获取IIS监控指标最佳实践礼包，其他更多问题欢迎咨询

<img src="https://wedoc.canway.net/imgs/img/小嘉.jpg" width="50%" height="50%">
