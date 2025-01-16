# Luban 游戏配置方案

![icon](docs/images/logo.png)

[![license](http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://opensource.org/licenses/MIT) ![star](https://img.shields.io/github/stars/focus-creative-games/luban?style=flat-square)

## 简介

Luban是一个强大、易用、优雅、稳定的游戏配置解决方案。它能满足从小型到超大型游戏项目的各类配置需求，支持多种数据格式和编程语言，具有出色的跨平台能力。

## 系统架构

luban/

├── src/ # 源代码目录

│ ├── Luban/ # 主程序

│ │ ├── Utils/ # 工具类

│ │ │ ├── DirectoryWatcher.cs # 文件监控

│ │ │ └── ConsoleUtil.cs # 控制台工具

│ ├── Luban.Lua/ # Lua支持

│ ├── Luban.Core/ # 核心功能

│ └── ... # 其他语言支持

### 核心组件

1. **主程序(Luban)**

   - 配置加载和解析
   - 代码生成管理
   - 数据验证
2. **工具模块(Utils)**

   - DirectoryWatcher: 文件变更监控
   - ConsoleUtil: 控制台交互优化
3. **语言支持模块**

   - C#, Java, Go, Lua等语言代码生成
   - 支持自定义模板

## 快速开始

### 1. 环境要求

- .NET SDK 8.0+
- 支持的游戏引擎:
  - Unity
  - Unreal
  - Cocos2x
  - Godot

### 2. 安装

# Luban - 游戏配置解决方案

## 项目结构分析

**luban/**

**├── docs/                 # 文档目录**

**├── images/              # 图片资源**

**├── scripts/             # 脚本文件**

**│   ├── format.bat       # Windows格式化脚本**

**│   └── format.sh        # Linux/Mac格式化脚本**

**├── src/                 # 源代码目录**

**│   ├── Luban/          # 主程序**

**│   ├── Luban.Bson/     # BSON序列化支持**

**│   ├── Luban.Core/     # 核心功能**

**│   ├── Luban.Cpp/      # C++代码生成**

**│   ├── Luban.CSharp/   # C#代码生成**

**│   └── ...             # 其他语言支持模块**

**├── .editorconfig       # 编辑器配置**

**├── .gitattributes      # Git属性配置**

**├── .gitignore          # Git忽略配置**

**├── .travis.yml         # Travis CI配置**

**├── LICENSE             # MIT许可证**

**└── README.md           # 项目说明文档**

## 核心特性

1. 多格式支持

* 支持Excel族文件(csv, xls, xlsx, xlsm)
* 支持JSON, XML, YAML, Lua等格式
* 可导出为binary, json, bson, xml, lua, yaml等格式
* 多语言生成
* C#, Java, Go, C++, Lua, Python
* TypeScript, PHP, Rust等
* 支持protobuf, flatbuffers, msgpack等消息方案
* 类型系统
* 支持OOP类型继承
* 可表达复杂的游戏配置数据
* 支持行为树、技能、剧情等复杂数据结构
* 跨平台支持
* 支持Windows, Linux, Mac
* 支持主流游戏引擎(Unity, Unreal, Cocos2x, Godot)
* 支持微信小游戏等平台
* 开发工具
* 数据校验功能
* 本地化支持
* 支持热更新方案

## 技术特点

* 模块化设计
* 清晰的代码生成管线
* 可扩展的插件系统
* 支持自定义数据格式
* 性能优化
* 高效的数据处理
* 快速的代码生成
* 优化的内存使用
* 开发体验
* 详细的错误提示
* 支持文件变更监控
* 标准化的配置工作流

## 使用场景

* 游戏配置数据管理
* 多语言项目开发
* 跨平台游戏开发
* 大型项目配置管理

## 许可证

项目采用MIT许可证，由Code Philosophy Technology Ltd.开发维护。

## 社区支持

* QQ群: 692890842
* Discord: https://discord.gg/dGY4zzGMJ4
* 邮箱: luban@code-philosophy.com

Checkpoint created.**restore**

如何使用这个项目？例如我需要在unity中使用luban进行配置

我来说明如何在Unity项目中使用Luban进行配置管理。

# Unity项目中使用Luban的步骤

## 1. 安装准备

* 安装必要环境:
* .NET SDK 8.0或更高版本
* Unity 2019.4或更高版本
* Excel(可选,如果使用Excel配置)
* 获取Luban工具:

  **   **# 方式1: 通过dotnet工具安装

  **   **dotnet** **tool** **install** **Luban** **--global

  ---

  **   **# 方式2: 从源码构建

  **   **git** **clone** **https://github.com/focus-creative-games/luban

  **   **cd** **luban

  **   **dotnet** **build

## 2. 项目配置

* 在Unity项目根目录创建配置目录结构:

  **MyGame/**

  **├── Assets/**

  **│   └── Scripts/**

  **│       └── Gen/        # 生成的代码将放在这里**

  **├── Configs/            # 配置文件目录**

  **│   ├── Defines/       # 数据结构定义**

  **│   └── Datas/         # Excel等数据文件**

  **└── Tools/             # 工具脚本目录**
* 创建配置定义文件 (例如 Configs/Defines/tables.xml):

  **<**module **name**=**"game"**>

  **    **<**bean **name**=**"Item"**>**

  **        **<**var **name**=**"id"** **type**=**"int"**/>**

  **        **<**var **name**=**"name"** **type**=**"string"**/>**

  **        **<**var **name**=**"desc"** **type**=**"string"**/>**

  **        **<**var **name**=**"price"** **type**=**"int"**/>**

  **    **</**bean**>

  ---

  **    **<**table **name**=**"TbItem"** **value**=**"Item"** **input**=**"item.xlsx"**/>**

  **</**module**>**
* 创建数据文件 (例如 Configs/Datas/item.xlsx):

  **id   | name      | desc           | price**

  **-----|-----------|----------------|-------**

  **1    | 木剑      | 新手武器       | 100**

  **2    | 铁剑      | 基础武器       | 200**

## 3. 生成代码和数据

* 创建生成脚本 (例如 Tools/gen.bat):

  **@**echo** **off

  **:: 生成C#代码**

  **luban gen --template_search_path Templates -j cfg **--csharp_dir Assets/Scripts/Gen --csharp_namespace** MyGame --conf Configs/Defines/tables.xml**

  **:: 生成二进制数据**

  **luban gen --template_search_path Templates -j cfg **--data_dir Assets/Resources/Config --conf Configs/**Defines/tables.xml**
* 运行生成脚本:

  **cd** **Tools**

  **./gen.bat**

## 4. 在Unity中使用

* 加载配置数据:

  **using** **MyGame**;

  **public** **class** **GameManager** : **MonoBehaviour**

  **{**

  **    **void** **Start**(**)

  **    **{

  **        // 初始化配置表**

  **        **var** tables = new **Tables**(**)**;**

  ---

  **        // 从Resources加载数据**

  **        tables.**LoadAll**(**)**;**

  ---

  **        // 使用配置数据**

  **        **var** item = tables.TbItem.**Get**(**1**)**;

  **        Debug.**Log**(**$"Item name: {**item**.**Name**}, price: {**item**.**Price**}"**)**;

  **    **}

  **}**

## 5. 开发工作流

* 实时生成:

  **# 监视配置文件变化并自动重新生成**

  **luban** **watch** **--template_search_path** **Templates** **-j** **cfg** **--csharp_dir** **Assets/Scripts/Gen** **--conf** **Configs/Defines/tables.xml**
* 编辑器集成:

  **#**if** UNITY_EDITOR**

  **[**UnityEditor**.**MenuItem**(**"Tools/Generate Configs"**)**]

  **public** **static** **void** **GenerateConfigs**(**)**

  **{**

  **    **string** genScript = Path.**Combine**(**Application.dataPath, **"../Tools/gen.bat"**)**;**

  **    System.Diagnostics.Process.**Start**(**genScript**)**;

  **}**

  **#**endif

## 高级特性

* 数据验证:

  **<**bean **name**=**"Item"**>

  **    **<**var **name**=**"id"** **type**=**"int"**/>**

  **    **<**var **name**=**"price"** **type**=**"int"** **range**=**"[0,]"**/>** **`<!-- 价格必须大于0 -->`**

  **</**bean**>**
* 多语言支持:

  **<**bean **name**=**"Item"**>

  **    **<**var **name**=**"name"** **type**=**"string"** **i18n**=**"true"**/>** **`<!-- 支持多语言 -->`**

  **</**bean**>**
* 引用检查:

  **<**bean **name**=**"Quest"**>

  **    **<**var **name**=**"itemReward"** **type**=**"int"** **ref**=**"item"**/>** **`<!-- 检查物品ID是否存在 -->`**

  **</**bean**>**

## 注意事项

1. 目录结构保持清晰,便于管理

* 定期备份配置文件
* 建议使用版本控制管理配置
* 可以根据需要调整生成的代码风格
* 建议启用数据验证,避免错误配置

## 常见问题

1. 生成失败:

* 检查.NET环境是否正确安装
* 确认配置文件格式正确
* 查看详细错误日志
* 数据加载失败:
* 确认生成路径正确
* 检查文件编码(推荐UTF-8)
* 验证数据格式完整性
* 性能优化:
* 可以使用二进制格式提高加载速度
* 考虑分表加载减少内存占用
* 必要时使用异步加载

Checkpoint created.**restore**

将架构和使用输出到readme-cn中

我将为这个项目创建一个详细的中文README文档。

README-cn.md1/2

**# Luban 游戏配置方案**


**[**![license]**(**http://img.shields.io/badge/license-MIT-blue.svg?s**tyle=flat-square**)**](**https://opensource.org/licenses/MIT**) ![star](**https://img.shields.io/github/stars/focus-creative**-games/luban?style=flat-square**)

**## 简介**

**Luban是一个强大、易用、优雅、稳定的游戏配置解决方案。它能满足从小型到超大型游戏项目的各类配置需求，支持多种数据格式和编程语言，具有出色的跨平台能力。**

**## 系统架构**

luban/

├── src/ # 源代码目录

│ ├── Luban/ # 主程序

│ │ ├── Utils/ # 工具类

│ │ │ ├── DirectoryWatcher.cs # 文件监控

│ │ │ └── ConsoleUtil.cs # 控制台工具

│ ├── Luban.Lua/ # Lua支持

│ ├── Luban.Core/ # 核心功能

│ └── ... # 其他语言支持

**### 核心组件**

**1. **主程序(Luban)****

**   - 配置加载和解析**

**   - 代码生成管理**

**   - 数据验证**

**2. **工具模块(Utils)****

**   - DirectoryWatcher: 文件变更监控**

**   - ConsoleUtil: 控制台交互优化**

**3. **语言支持模块****

**   - C#, Java, Go, Lua等语言代码生成**

**   - 支持自定义模板**

**## 快速开始**

**### 1. 环境要求**

**- .NET SDK 8.0+**

**- 支持的游戏引擎:**

**  - Unity**

**  - Unreal**

**  - Cocos2x**

**  - Godot**

**### 2. 安装**

bash:README-cn.md

# 通过dotnet工具安装

dotnet tool install Luban --global

# 或从源码构建

git clone https://github.com/focus-creative-games/luban

cd luban

dotnet build
