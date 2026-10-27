# handoff

**检查智能体之间的交接是否带齐了必需信息。**

`handoff` —— 按交接协议核对传递的字段，标出缺失与被截断的上下文

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`handoff.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install chiedkner-handoff
```

装完直接用命令名调用：

```bash
handoff --help
```

也可以不用安装，直接把 `handoff.py` 拷走用——它只依赖标准库。

## 为什么需要它

把交接质量量化成「必需字段的携带率」

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 多智能体交接 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python handoff.py --file input.txt
python handoff.py --text "示例内容"
python handoff.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分组靠标签与关键词相似度，分错组时不保证可解释。
- 不评估分组质量。

## 跑测试

```bash
python test_handoff.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/chiedkner/handoff>

---

## 关于作者

chiedkner 做多智能体交接相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://chiedkner.github.io>
- 仓库：<https://github.com/chiedkner/handoff>

## 许可

MIT，见 [LICENSE](LICENSE)。
