# 如何使用 Hermes Agent 稳定爬取公众号文章

- 来源（飞书 Wiki）：https://waytoagi.feishu.cn/wiki/OHC6wrM37iapyVk9BD8c7xXqn4c
- 原文链接（公众号）：https://mp.weixin.qq.com/s/3SSECMxYl4ZmbT6FSBs9kA
- 抓取时间：2026-04-12

---

> 原创：DracoVibeCoding（Draco 正在 VibeCoding）
> 
> 公众号发布时间：2026-04-11 16:51（澳大利亚）

## 背景

Browser Use 是 Hermes Agent 官方推荐的云端浏览器自动化提供商之一。

4 月 9 日，Browser Use 官宣：Hermes Agent 可以免费试用 Browser Use：
- 无限时长
- 免费 proxy
- 持久化鉴权

## 获取 Browser Use API Key

1. 登录 Browser Use 官网：https://browser-use.com/
2. 点击右上角「Login」登录
3. 进入 Settings → API Keys
4. 点击「Create API KEY」创建 Key
5. 复制 API Key

## 配置 Hermes Agent

把 API Key 写入 Hermes Agent 的环境文件：`~/.hermes/.env`

## 封装 skill 的提示词

将下面的提示词发给 Hermes Agent 让它自动封装：

> 请使用 Browser Use 封装一个爬取微信公众号文章的 skill；我已经将 Browser Use 的 API KEY 填写在了你的 `.env` 文件中

作者称：大概 10 分钟之后封装完成。

## 端到端测试与扩展

封装好之后，可以拿任意一篇公众号文章做端到端测试；并可进一步扩展：
- 获取文章内容后，写入飞书文档（保持格式）

作者补充：如果是首次封装，可能需要在格式与飞书文档规范上做更多细节调试。

## 备选：纯本地 CamoFox

如果担心 Browser Use 未来收费，可以用 Hermes Agent 推荐的 CamoFox 做一个纯本地版 skill。

## 相关开源

作者将两个版本的 skills 发布在 Draco-Skills-Collection：
- Browser Use 版本：https://github.com/dracohu2025-cloud/draco-skills-collection/tree/main/wechat-article-browseruse
- CamoFox 版本：https://github.com/dracohu2025-cloud/draco-skills-collection/tree/main/wechat-article-camofox

