### 请求地址

/api/c/compapi/v2/cc/bind_role_privilege/

### 请求方法

POST

### 功能描述

绑定角色权限

### 请求参数

#### 通用参数

| 字段 | 类型 | 必选 | 描述 |
|-----------|------------|--------|------------|
| bk_app_code | string | 是 | 应用 ID |
| bk_app_secret| string | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用ID -&gt; 基本信息 获取 |
| bk_token | string | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username | string | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |

#### 接口参数

| 字段 | 类型 | 必选 | 描述 |
|-----------|------------|--------|------------|
| bk_supplier_account | string | 是 | 开发商账号 |
| bk_obj_id | string | 是 | 模型 ID |
| bk_property_id | string | 是 | 模型对应用户角色属性 ID |
| data | list | 否 | 角色权限数据，输入为空数组则不绑定任何权限 |

#### data

| 字段 | 类型 | 必选 | 描述 |
|-----------|------------|--------|------------|
| hostupdate | string | 否 | 主机编辑 |
| hosttrans | string | 否 | 主机转移 |
| topoupdate | string | 否 | 主机拓扑编辑 |
| customapi | string | 否 | 自定义 api |
| proconfig | string | 否 | 进程管理 |

### 请求参数示例

```json
{
    "bk_app_code": "esb_test",
    "bk_app_secret": "xxx",
    "bk_token": "xxx",
    "bk_supplier_account": "123456789",
    "bk_obj_id": "biz",
    "bk_property_id": "test",
    "data": [
        "hostupdate",
        "hosttrans",
        "topoupdate",
        "customapi",
        "proconfig"
    ]
}
```

### 返回结果示例

```json
{
    "result": true,
    "code": 0,
    "message": "success",
    "data": "success"
}
```

### 返回结果参数说明

| 字段 | 类型 | 描述 |
|-----------|-----------|-----------|
| result | bool | 请求成功与否，true:请求成功，false:请求失败 |
| code | string | 组件返回错误编码 |
| message | string | 请求失败返回的错误消息 |
| data | object | 请求成功返回的数据 |
