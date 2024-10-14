# 快速开始
## 环境安装

在本项目中，执行下列指令即可完成项目的安装
```
pip install -e .
```

## key配置

为确保项目正常运行，**请在项目内新建`.env`文件，并在其中设置你的API密钥**，你可以根据下列例子写入对应的 key，即可成功运行调用,目前默认使用 zhipuai，你可以仅写入`ZHIPUAI_API_KEY`即可使用。

```
ZHIPUAI_API_KEY=
```

如果在从Hugging Face下载模型时遇到速度极慢或无法下载的问题，请在.env文件中设置`HF_ENDPOINT`的值为`https://hf-mirror.com`。请注意，某些Hugging Face仓库可能需要访问权限（例如Jina Ai）。为此，请注册一个Hugging Face账号，并在.env文件中添加`HF_TOKEN`。你可以在[这里](https://huggingface.co/settings/tokens)找到并获取你的token。

```
HF_HOME='temp/huggingface_cache/'
HF_ENDPOINT='https://hf-mirror.com'
OPENAI_API_KEY=
OPENAI_API_BASE=
ZHIPUAI_API_KEY=
BAIDU_API_KEY=
OPENAI_API_MODEL=
HF_TOKEN=
```

### 运行

以下给出 prompt 以及 agent 的相关应用方式，在运行前请确保你已经新建`.env`文件：

```bash
# 运行prompt webui前端
python3 run/tianji_prompt_webui.py

# 运行agent前端
streamlit run run/metagpt_webui.py

# 运行langchain前端
python run/demo_rag_langchain_onlinellm.py
```

## 开发环境配置

在进行项目开发与贡献之前，在保证key的正确设定后，你还需要在提交 pull request 前进行格式检查。你可以参考下列方式进行 pre-commit 的安装，在 commit 环节将会看到变更文件格式会被自动修改。

```
pip install pre-commit
pre-commit install
git add .
git commit -m "提交信息"
git push
```

这一步，你需要反复执行下列两步,直到 commit 成功 （该过程会帮助你自动修复绝大部分格式错误，但对于某些复杂格式需要自己手动根据提示修改。）

```
git add .
git commit -m "提交信息"
```

若全部成功，你将会看到类似如下信息显示：

```
[main 2333] rebuild code standard
 5 files changed, 4 insertions(+), 3 deletions(-)
```
