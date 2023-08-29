## 嘉为蓝鲸AD插件使用说明

## 使用说明

### 插件功能

AD Exporter用于采集Windows Active Directory域控制器的指标，通过 Windows Management Instrumentation (WMI) 提供的接口来采集数据。

### 版本支持

操作系统支持: windows

是否支持arm: 否

**组件支持版本：**

可以在支持 WMI 的 Windows 操作系统上采集数据。

**是否支持远程采集:**

否

### 参数说明

AD exporter采集目前只可以设置日志级别参数，直接下发到windows服务器即可。

### 使用指引

### 指标简介
| **指标ID**                                                           | **指标中文名**                   | **维度ID**        | **维度含义**   | **单位** |
| -------------------------------------------------------------------- | -------------------------------- | ----------------- | -------------- | -------- |
| windows_ad_up                                                        | AD插件运行状态                   | -                 | -              | -        |
| windows_ad_address_book_operations_total                             | AD地址簿操作总数                 | operation         | 操作           | -        |
| windows_ad_approximate_highest_distinguished_name_tag                | AD对象估计峰值                   | -                 | -              | -        |
| windows_ad_binds_total                                               | AD总绑定数                       | bind_method       | 绑定方式       | -        |
| windows_ad_database_operations_total                                 | AD数据库操作总数                 | operation         | 操作           | -        |
| windows_ad_link_values_cleaned_total                                 | AD清理的链接值总数               | -                 | -              | -        |
| windows_ad_searches_total                                            | AD搜索总数                       | scope             | 范围           | -        |
| windows_ad_tombstoned_objects_collected_total                        | AD回收的删除对象总数             | -                 | -              | -        |
| windows_ad_tombstoned_objects_visited_total                          | AD访问的删除对象总数             | -                 | -              | -        |
| windows_ad_atq_average_request_latency                               | AD中活动线程队列平均请求延迟时间 | -                 | -              | ms       |
| windows_ad_atq_current_threads                                       | AD当前活动线程队列线程数         | service           | 服务           | -        |
| windows_ad_atq_estimated_delay_seconds                               | AD中活动线程队列预计延迟时间     | -                 | -              | s        |
| windows_ad_atq_outstanding_requests                                  | AD中活动线程队列待处理请求数     | -                 | -              | -        |
| windows_ad_change_monitor_updates_pending                            | AD变更监视器待处理更新数         | -                 | -              | -        |
| windows_ad_change_monitors_registered                                | AD已注册变更监视器数             | -                 | -              | -        |
| windows_ad_directory_operations_total                                | AD目录操作总数                   | operation, origin | 操作, 操作来源 | -        |
| windows_ad_directory_search_suboperations_total                      | AD目录搜索子操作总数             | -                 | -              | -        |
| windows_ad_directory_service_threads                                 | AD目录服务线程数                 | -                 | -              | -        |
| windows_ad_ldap_active_threads                                       | AD LDAP活动线程数                | -                 | -              | -        |
| windows_ad_ldap_last_bind_time_seconds                               | AD LDAP最近绑定时间              | -                 | -              | s        |
| windows_ad_ldap_opened_connections_total                             | AD已打开的LDAP连接总数           | type              | 类型           |          |
| windows_ad_ldap_closed_connections_total                             | AD已关闭的LDAP连接总数           | -                 | -              | -        |
| windows_ad_ldap_searches_total                                       | AD LDAP搜索总数                  | -                 | -              | -        |
| windows_ad_ldap_udp_operations_total                                 | AD LDAP UDP操作总数              | -                 | -              | -        |
| windows_ad_ldap_writes_total                                         | AD LDAP写入总数                  | -                 | -              | -        |
| windows_ad_name_cache_hits_total                                     | AD名称缓存命中总数               | -                 | -              | -        |
| windows_ad_name_cache_lookups_total                                  | AD名称缓存查找总数               | -                 | -              | -        |
| windows_ad_name_translations_total                                   | AD名称翻译总数                   | target_name       | 目标名称       | -        |
| windows_ad_phantom_objects_cleaned_total                             | AD清理的幻影对象总数             | -                 | -              | -        |
| windows_ad_phantom_objects_visited_total                             | AD访问的幻影对象总数             | -                 | -              | -        |
| windows_ad_replication_data_intersite_bytes_total                    | AD跨站点复制数据字节总数         | direction         | 方向           | bytes    |
| windows_ad_replication_data_intrasite_bytes_total                    | AD站点内复制数据字节总数         | direction         | 方向           | bytes    |
| windows_ad_replication_highest_usn                                   | AD复制最高更新序列号             | state             | 状态           | -        |
| windows_ad_replication_inbound_link_value_updates_remaining          | AD入站链接值更新剩余次数         | -                 | -              | -        |
| windows_ad_replication_inbound_objects_filtered_total                | AD入站过滤对象总数               | -                 | -              | -        |
| windows_ad_replication_inbound_objects_updated_total                 | AD入站更新对象总数               | -                 | -              | -        |
| windows_ad_replication_inbound_properties_filtered_total             | AD入站过滤属性总数               | -                 | -              | -        |
| windows_ad_replication_inbound_properties_updated_total              | AD入站更新属性总数               | -                 | -              | -        |
| windows_ad_replication_inbound_sync_objects_remaining                | AD入站同步对象剩余次数           | -                 | -              | -        |
| windows_ad_replication_pending_operations                            | AD待处理的复制操作数             | -                 | -              | -        |
| windows_ad_replication_pending_synchronizations                      | AD待处理的同步操作数             | -                 | -              | -        |
| windows_ad_replication_sync_requests_schema_mismatch_failure_total   | AD同步请求模式不匹配失败总数     | -                 | -              | -        |
| windows_ad_replication_sync_requests_success_total                   | AD同步请求成功总数               | -                 | -              | -        |
| windows_ad_replication_sync_requests_total                           | AD同步请求总数                   | -                 | -              | -        |
| windows_ad_sam_computer_creation_requests_total                      | AD SAM计算机创建请求总数         | -                 | -              | -        |
| windows_ad_sam_computer_creation_successful_requests_total           | AD成功的SAM计算机创建请求总数    | -                 | -              | -        |
| windows_ad_sam_enumerations_total                                    | AD SAM枚举总数                   | -                 | -              | -        |
| windows_ad_sam_group_evaluation_latency                              | AD SAM组评估延迟时间             | evaluation_type   | 评估类型       | -        |
| windows_ad_sam_group_membership_evaluations_nontransitive_total      | AD非传递的SAM组成员评估总数      | -                 | -              | -        |
| windows_ad_sam_group_membership_evaluations_total                    | AD SAM组成员评估总数             | group_type        | 组类型         | -        |
| windows_ad_sam_group_membership_evaluations_transitive_total         | AD传递的SAM组成员评估总数        | -                 | -              | -        |
| windows_ad_sam_group_membership_global_catalog_evaluations_total     | AD全局目录的SAM组成员评估总数    | -                 | -              | -        |
| windows_ad_sam_membership_changes_total                              | AD SAM成员变更总数               | -                 | -              | -        |
| windows_ad_sam_password_changes_total                                | AD SAM密码更改总数               | -                 | -              | -        |
| windows_ad_sam_query_display_requests_total                          | AD SAM查询显示请求总数           | -                 | -              | -        |
| windows_ad_sam_user_creation_requests_total                          | AD SAM用户创建请求总数           | -                 | -              | -        |
| windows_ad_sam_user_creation_successful_requests_total               | AD成功的SAM用户创建请求总数      | -                 | -              | -        |
| windows_ad_security_descriptor_propagation_access_wait_total_seconds | AD安全描述符传播访问等待总秒数   | -                 | -              | s        |
| windows_ad_security_descriptor_propagation_events_queued             | AD安全描述符传播排队事件总数     | -                 | -              | -        |
| windows_ad_security_descriptor_propagation_events_total              | AD安全描述符传播事件总数         | -                 | -              | -        |
| windows_ad_security_descriptor_propagation_items_queued_total        | AD安全描述符传播排队项目总数     | -                 | -              | -        |
| process_cpu_seconds_total                                            | AD监控探针进程CPU秒数总计        | -                 | -              | s        |
| process_max_fds                                                      | AD监控探针进程最大文件描述符数   | -                 | -              | -        |
| process_open_fds                                                     | AD监控探针进程打开文件描述符数   | -                 | -              | -        |
| process_resident_memory_bytes                                        | AD监控探针进程常驻内存大小       | -                 | -              | bytes    |
| process_virtual_memory_bytes                                         | AD监控探针进程虚拟内存大小       | -                 | -              | bytes    |
| windows_exporter_collector_duration_seconds                          | AD监控探针采集持续时间           | collector         | 采集目标       | s        |
| windows_exporter_collector_success                                   | AD监控探针采集成功状态           | collector         | 采集目标       | -        |

### 版本日志

#### weops_AD_exporter 2.6.0

- weops调整

添加“小嘉”微信即可获取AD监控指标最佳实践礼包，其他更多问题欢迎咨询

<img src="https://wedoc.canway.net/imgs/img/小嘉.jpg" width="50%" height="50%">
