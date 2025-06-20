# ManCN - Linux手册页中文翻译工具

一个专为中国开发者设计的Linux man页面翻译工具，帮助快速理解英文技术文档。

## 功能特点

- 🚀 **快速翻译**: 一键翻译Linux man页面为中文
- 💾 **智能缓存**: 本地缓存翻译结果，避免重复翻译
- 🔧 **多引擎支持**: 支持Google、百度、有道翻译
- 📝 **格式保持**: 保留原始格式，只翻译必要内容
- ⚡ **命令行友好**: 简单易用的命令行界面

## 安装

### 方法一：直接运行

```bash
# 克隆项目
git clone https://github.com/your-username/man-cn.git
cd man-cn

# 安装依赖
pip install -r requirements.txt

# 运行
python man_cn.py fork
```

### 方法二：安装到系统

```bash
# 复制到系统路径
sudo cp man_cn.py /usr/local/bin/manc
sudo chmod +x /usr/local/bin/manc

# 创建符号链接
ln -s /usr/local/bin/manc ~/.local/bin/manc
```

## 使用方法

### 基本使用

```bash
# 翻译fork命令的手册页
manc fork

# 翻译特定节的手册页
manc fork 2

# 强制重新翻译（忽略缓存）
manc -r fork
```

### 缓存管理

```bash
# 查看缓存列表
manc --list-cache

# 清空所有缓存
manc --clear-cache

# 指定缓存目录
manc --cache-dir ~/my_cache fork
```

### 切换翻译引擎

```bash
# 使用Google翻译（默认）
manc -t google fork

# 使用百度翻译
manc -t baidu fork

# 使用有道翻译
manc -t youdao fork
```

## 配置

### 百度翻译API配置

如果要使用百度翻译，需要设置环境变量：

```bash
export BAIDU_TRANSLATE_APP_ID="your_app_id"
export BAIDU_TRANSLATE_SECRET_KEY="your_secret_key"
```

### 有道翻译API配置

```bash
export YOUDAO_APP_KEY="your_app_key"
export YOUDAO_APP_SECRET="your_app_secret"
```

## 项目结构

```
man-cn/
├── man_cn.py          # 主程序
├── requirements.txt   # 依赖包
├── README.md         # 说明文档
└── examples/         # 使用示例
```


## 常见问题

### Q: 翻译结果不准确怎么办？
A: 可以尝试切换不同的翻译引擎，或者使用`-r`参数强制重新翻译。

### Q: 如何清除特定命令的缓存？
A: 目前需要手动删除`~/.man_cn_cache/`目录下对应的JSON文件。

### Q: 支持其他语言吗？
A: 目前只支持英译中，后续版本会考虑支持更多语言。

### Q: 可以离线使用吗？
A: 需要网络连接调用翻译API，但缓存的内容可以离线查看。

## 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 致谢

- Author-Claude-sonnet-4.0

## 更新日志

### v1.0.0 
- 初始版本发布
- 支持基本翻译功能
- 实现本地缓存机制
- 支持多种翻译引擎

-----------------------------------------------------------------------------------------------
