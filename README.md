# Virgenta - 病毒基因组注释系统

基于HyperFusion Cortex（HFC）的轻量病毒基因组注释系统——高效解析泛基因组非核心基因突变。Virgenta是一个全自动预测病毒基因中的蛋白质序列并生成报告的系统。

## 项目概述

Virgenta利用先进的机器学习模型（MSA_ResGRUNet），对病毒基因组序列进行分析，识别基因编码区域，预测蛋白质功能，并自动生成详细的注释报告。系统包含前后端分离架构，提供直观的可视化界面展示基因组注释结果。

### 核心功能

- **基因组注释**: 上传FASTA格式的病毒序列，自动进行基因识别和功能注释
- **蛋白质预测**: 利用深度学习模型预测病毒基因编码的蛋白质功能
- **可视化界面**: 交互式展示病毒基因组结构和注释信息
- **报告生成**: 自动生成TXT格式详细分析报告和GFF格式标准注释文件
- **报告管理**: 系统化管理历史分析报告，便于检索和比较

## 技术架构

### 后端

- **Python Flask API**: 提供RESTful API服务
- **深度学习模型**: 使用PyTorch实现的MSA_ResGRUNet模型，结合多尺度卷积、残差连接和GRU进行蛋白质功能预测
- **生物信息学处理**: 使用BioPython处理序列信息
- **报告生成系统**: 自动生成结构化的分析报告和标准GFF文件

### 前端

- **Vue.js框架**: 构建响应式单页面应用
- **交互式可视化**: 动态展示基因组结构和注释信息
- **文件上传处理**: 支持大型FASTA文件的上传和分析

## 快速开始

### 环境要求

- Python 3.8+
- Node.js 14+
- 支持CUDA的GPU（推荐用于模型运行）

### 安装步骤

1. 克隆项目仓库
```bash
git clone <repository-url>
cd protein_prediction
```

2. 安装Python依赖
```bash
pip install -r requirements.txt
```

3. 安装前端依赖
```bash
cd frontend
npm install
```

### 运行系统

1. 启动后端API服务
```bash
python api.py
```

2. 启动前端开发服务器
```bash
cd frontend
npm run serve
```

3. 在浏览器中访问 `http://localhost:8080`

## 文件结构

```
protein_prediction/
├── api.py                # 主要API服务入口
├── chat_api.py           # 报告生成API
├── generate_gff.py       # GFF文件生成工具
├── main.py               # 应用程序主入口
├── model.py              # 深度学习模型定义
├── pre_processing.py     # 数据预处理模块
├── train.py              # 模型训练脚本
├── test.py               # 测试脚本
├── requirements.txt      # Python依赖清单
├── model/                # 预训练模型存储
├── gff/                  # GFF报告输出目录
├── result/               # 分析结果输出目录
├── summary/              # 分析报告输出目录
├── train_data/           # 训练数据集
├── test_data/            # 测试数据集
└── frontend/             # 前端应用
    ├── src/              # 源代码
    │   ├── App.vue       # 主应用组件
    │   ├── components/   # Vue组件
    │   │   ├── GeneVisualization.vue  # 基因组可视化组件
    │   │   └── SummaryReport.vue      # 报告管理组件
    │   └── main.js       # 应用入口点
    ├── public/           # 静态资源
    ├── package.json      # 前端依赖配置
    └── vue.config.js     # Vue配置
```

## 使用指南

1. 在系统界面选择"基因组注释"选项卡
2. 上传FASTA格式的病毒基因组序列文件
3. 系统自动进行分析和注释
4. 查看可视化的基因组结构图
5. 点击"查看txt报告"或"查看GFF报告"获取详细分析结果
6. 可在"总报告管理"页面查看和管理历史分析报告

## 模型说明

系统核心使用MSA_ResGRUNet深度学习模型，结合了多尺度卷积分析、残差连接和门控循环单元，特别针对病毒基因组序列特征优化，能高效识别非核心基因突变。

## 许可证

[项目许可证信息]

## 联系方式

[项目联系人信息] 