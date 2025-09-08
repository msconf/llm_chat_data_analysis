# [中文](README.md) | [English](README-en.md)

# 🚀 llm_chat_data_analysis

Analyze data through natural language instructions and output structured results.
HTTP requests, ready to use out of the box, no coding required.

> 📌 Project Objective: Complete data analysis through conversation.

---

## 📦 Quick Start

## 1. Download project

```bash
git clone https://github.com/msconf/llm_chat_data_analysis.git
cd llm_chat_data_analysis
```

## 2. Configuration Project

Modify the <span style="color:red;">config.json</span> file and configure your data path, API key, and access method:

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

#### 📌 Configuration Instructions：

    SERVER_PORT ：Server port

    OPENAI_API_KEY ：OpenAI API key
    OPENAI_API_BASE_URL ：OpenAI API url
    OPENAI_API_MODEL ：OpenAI Model Name
    OPENAI_API_EXTRA_BODY ：Extra parameters, JSON string format

    DB_HOST ：Database address
    DB_PORT ：Database port
    DB_USER ：Username
    DB_PASSWORD ：Password
    DB_NAME ：Database name

## 3. Start service

Run the following command to start the service:

```bash
chmod 775 ./app.bin && ./app.bin
 ```

## 4.How to use

#### Parameter Description：

    user_query *：Natural user query statement
    sql_text：SQL statement (query statement of the data to be analyzed)
    json_datas：The data to be analyzed, in JSON format

    ！At least one of the parameters json_datas or sql_text is required. If both parameters are provided, the sql_text parameter will be used preferentially.

#### Request format：

    Request address：http://x.x.x.x:x/analysis_data
    Request method：POST

#### Request parameters：

```json
{
  "user_query": "Check stocks with a price greater than 20 on August 22, 2025",
  "sql_text": "select * from stock_daily_quote where trade_date > '2025-08-20'",
  "json_datas": [
    {
      "student_id": "S0001",
      "name": "Zhang Xiaoming",
      "gender": "Male",
      "class": "Class 1",
      "Scores": 88
    },
    {
      "student_id": "S0002",
      "name": "LiXiaohong",
      "gender": "Woman",
      "class": "Class 2",
      "Scores": 95
    }
  ]
}
```
