# [中文](README.md) | [English](README-en.md)
# 🚀 llm_chat_data_analysis

通过自然语言指令，进行数据分析，并输出结构化结果。  
HTTP请求，开箱即用，无需编写代码。

> 📌 项目目标：通过对话完成数据分析。

---

## 📦 快速开始

## 1. 下载项目

```bash
git clone https://github.com/msconf/llm_chat_data_analysis.git
cd llm_chat_data_analysis
```

## 2. 配置项目

修改 config.json 文件，配置你的数据路径、API 密钥和访问方式：

```json
{
  "SERVER_PORT": "8001",
  "LLM": {
    "OPENAI_API_KEY": "xxxx",
    "OPENAI_API_BASE_URL": "http://x.x.x.x:x/v1",
    "OPENAI_API_MODEL": "Qwen",
    "OPENAI_API_EXTRA_BODY": "{\"chat_template_kwargs\":{\"enable_thinking\":false}}"
  },
  "DB": {
    "DB_HOST": "x.x.x.x",
    "DB_PORT": "3306",
    "DB_USER": "root",
    "DB_PASSWORD": "xxxx",
    "DB_NAME": "xxxx"
  }
}
```

#### 📌 配置说明：

    SERVER_PORT ：服务端口

    OPENAI_API_KEY ：OpenAI API 密钥
    OPENAI_API_BASE_URL ：OpenAI API 地址
    OPENAI_API_MODEL ：OpenAI 模型名称
    OPENAI_API_EXTRA_BODY ：OpenAI API 额外参数，JSON 格式

    DB_HOST ：数据库地址
    DB_PORT ：数据库端口
    DB_USER ：用户名
    DB_PASSWORD ：密码
    DB_NAME ：数据库名称

## 3. 启动服务

运行以下命令启动服务：

```bash
chmod 775 ./app.bin && ./app.bin
 ```

## 4.如何使用

#### 参数说明：

    user_query *：用户自然查询语句
    sql_text：SQL语句（需要分析的数据的查询语句）
    json_datas：需要分析的数据，JSON格式

    json_datas、sql_text 参数至少需要一个，如果同时提供两个参数，则优先使用sql_text参数。

#### 请求格式：

    请求地址：http://x.x.x.x:x/analysis_data
    请求方式：POST

#### 请求参数：

```json
{
  "user_query": "查询2025年8月22的股价大于20的股票",
  "sql_text": "select * from stock_daily_quote where trade_date > '2025-08-20'",
  "json_datas": [
    {
      "student_id": "S0001",
      "name": "张小明",
      "gender": "男",
      "class": "1班",
      "成绩": 88
    },
    {
      "student_id": "S0002",
      "name": "李小红",
      "gender": "女",
      "class": "2班",
      "成绩": 95
    }
  ]
}
```
