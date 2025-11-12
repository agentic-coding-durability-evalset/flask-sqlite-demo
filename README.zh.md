# Flask SQLite Demo

一个基于 [Flask](https://flask.palletsprojects.com/) 和 SQLite 的 Python Web 应用示例项目。使用 SQLAlchemy 作为 ORM，展示了如何构建传统的同步 Web 应用。

## 技术栈

- **Python**: 3.13+
- **Flask**: 3.1.2+
- **Flask-SQLAlchemy**: 3.1.1+
- **SQLAlchemy**: 2.0.41+
- **Pytest**: 8.4.2+ (测试框架)

## 项目结构

```
flask-sqlite-demo/
├── app/
│   ├── main.py              # Flask 应用入口
│   ├── domain/
│   │   └── models.py        # 数据模型定义
│   └── routes/
│       └── hero_route.py   # Hero API 路由
├── db/
│   ├── schema.ddl          # 数据库模式定义
│   └── demo.sqlite3        # SQLite 数据库文件
├── tests/                  # 测试文件
├── pyproject.toml          # 项目配置和依赖
├── Justfile                # Just 构建工具配置
└── README.md
```

## 功能特性

- RESTful API 设计
- SQLAlchemy ORM 集成
- Flask Blueprint 路由组织
- SQLite 数据库支持
- 单元测试支持

## 快速开始

### 前置要求

- Python 3.13 或更高版本
- pip 或 uv (推荐)

### 安装和运行

```bash
# 创建虚拟环境（推荐）
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 安装依赖
pip install -e ".[dev]"

# 或使用 uv（更快）
uv pip install -e ".[dev]"

# 运行应用
python -m app.main
```

应用将在 `http://localhost:5000` 启动（默认端口）。

### 环境变量

可以通过环境变量配置数据库连接：

```bash
export SQLALCHEMY_DATABASE_URI="sqlite:///path/to/db/demo.sqlite3"
```

如果不设置，默认使用 `./db/demo.sqlite3`。

## API 端点

### 根路径
```http
GET http://localhost:5000/
```
响应: `Flask is working`

### Hero API

所有 Hero 相关的 API 端点定义在 `/app/routes/hero_route.py` 中，路径前缀为 `/heros`。

## 数据库

### 数据库初始化

数据库模式定义在 `db/schema.ddl` 中。应用启动时会自动初始化数据库连接。

## 参考资源

- [Flask 官方文档](https://flask.palletsprojects.com/)
- [Flask-SQLAlchemy 文档](https://flask-sqlalchemy.palletsprojects.com/)
- [SQLAlchemy 文档](https://docs.sqlalchemy.org/)
