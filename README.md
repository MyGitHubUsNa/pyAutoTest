# pyautoTest Web UI 自动化项目

#### 特点：

* 全局配置浏览器启动/关闭。
* 测试用例运行失败自动截图。
* 测试用例运行失败可以重跑。
* 测试数据参数化。

#### 安装：

```shell
$ pip install -r requirements.txt
```

#### 配置：

在 __conftest.py__ 文件配置

```python
# 配置浏览器驱动类型。
driver_type = "chrome"

# 配置运行的 URL
url = "https://www.baidu.com"

# 失败重跑次数
rerun = "3"

# 运行测试用例的目录或文件
cases_path = "./test_dir/"

# 配置driver
    if driver_type == "chrome":
        # 本地chrome浏览器
        option = webdriver.ChromeOptions()
        option.add_argument("disable-infobars")		# 去除浏览器受控制的提醒
        path = "【chromedriver.exe所在的绝对路径】"
        driver = webdriver.Chrome(options=option, executable_path=path)
```

#### 运行：

```shell
$ python run_tests.py  (回归模式，生成HTML报告)
$ python run_tests.py -m debug  (调试模式)
```
注： 不支持在编辑器中运行，请在 cmd（windows）/终端(Linux)下执行。
