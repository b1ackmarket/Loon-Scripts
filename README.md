# Loon-Scripts

Loon脚本和插件集合

## WPS签到 Loon插件使用说明

### 插件介绍

WPS签到插件可以自动完成WPS每日签到，获取会员时长奖励。本插件支持两种验证码识别方式：百度OCR和QwenOCR，可以根据个人需求选择使用。

### 功能特点

- 自动获取并保存Cookie
- 自动识别验证码并完成签到
- 支持百度OCR和QwenOCR两种验证码识别方式
- 可配置自动兑换会员天数
- 可设置最大重试次数

### 安装方法

#### 方法一：直接安装

1. 打开Loon，点击底部的"配置"
2. 点击"插件"
3. 点击右上角的"+"
4. 输入插件链接：`https://raw.githubusercontent.com/b1ackmarket/Loon-Scripts/main/WPS签到.plugin`
5. 点击"安装"

#### 方法二：手动添加

1. 打开Loon，点击底部的"配置"
2. 点击"插件"
3. 点击右上角的"+"
4. 输入以下信息：
   - 名称：WPS签到
   - URL：留空
   - 内容：复制[WPS签到.plugin](https://raw.githubusercontent.com/b1ackmarket/Loon-Scripts/main/WPS签到.plugin)的内容
5. 点击"安装"

### 配置说明

安装插件后，需要配置以下参数：

#### 必选参数

- **OCR_TYPE**：OCR服务类型
  - `1`：百度OCR（默认）
  - `2`：QwenOCR

#### 根据OCR_TYPE选择必填参数

- 当OCR_TYPE=1（百度OCR）时：
  - **AK**：百度API的API Key
  - **SK**：百度API的Secret Key

- 当OCR_TYPE=2（QwenOCR）时：
  - **QWEN_COOKIE**：QwenOCR的自定义Cookie

#### 可选参数

- **DAY**：自动兑换会员天数，默认为0（不自动兑换）
- **MAX_RETRIES**：最大重试次数，默认为5次

### 获取必要参数

#### 获取WPS Cookie

1. 安装插件后，打开WPS官网（https://zt.wps.cn）并登录
2. 登录成功后，Loon会自动获取Cookie并保存

#### 获取百度OCR参数（如果使用百度OCR）

1. 注册百度AI开放平台账号：https://ai.baidu.com/
2. 创建一个OCR应用，获取API Key（AK）和Secret Key（SK）
3. 在插件配置中填入AK和SK

#### 获取QwenOCR Cookie（如果使用QwenOCR）

1. 访问QwenOCR网站：https://qwenocr.aibot2023.workers.dev/
2. 获取自定义Cookie
3. 在插件配置中填入QWEN_COOKIE

### 使用说明

1. 完成插件安装和配置后，插件会在每天早上8点自动运行（可以在插件设置中修改定时）
2. 插件会自动获取验证码图片，使用选定的OCR服务识别，并完成签到
3. 签到成功后，会显示获得的会员时长和账户信息

### 常见问题

1. **签到失败怎么办？**
   - 检查Cookie是否有效，可以重新登录WPS获取Cookie
   - 检查OCR参数是否正确
   - 增加MAX_RETRIES参数值，提高重试次数

2. **如何切换OCR服务？**
   - 在插件设置中修改OCR_TYPE参数，并确保填写了对应的必要参数

3. **如何手动触发签到？**
   - 在Loon的"插件"页面，找到WPS签到插件，点击右侧的运行按钮

### 注意事项

1. 使用百度OCR需要注册百度AI开放平台账号，可能有API调用次数限制
2. 使用QwenOCR需要获取自定义Cookie
3. 插件默认每天早上8点运行，可以根据需要修改定时
4. 如果长时间不使用WPS，Cookie可能会失效，需要重新获取

### 更新日志

- 2024-10-14：增加QwenOCR选项，支持两种验证码识别方式
- 2024-10-13：初始版本发布，使用百度OCR识别验证码

### 作者信息

- 原作者：小白脸
- 修改：Yao Qinsher
- 主页：https://github.com/b1ackmarket