# Web-Proxy
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

[English](README.md) | 简体中文

## 项目简介
Web-Proxy 是一个运行在 Cloudflare 边缘节点上的轻量级网页代理。
项目同时支持 Cloudflare Workers 和 Cloudflare Pages（Advanced Mode）。

## 目录结构
- `worker.js`：Cloudflare Workers 入口（Module Worker 格式）
- `WebProxy/_worker.js`：Cloudflare Pages 入口（Advanced Mode）
- `LICENSE`：Apache License 2.0 许可证全文
- `NOTICE`：第三方归属与声明

## 快速开始
1. Fork 或克隆本仓库。
2. 选择部署目标：
   - Workers：使用 `worker.js`
   - Pages：使用 `WebProxy文件夹`或`WebProxy.zip`
3. 完成部署并访问你的域名。
4. 打开 `/works` 验证，期望返回 `it works`。

## 部署说明

### 方案 A：Cloudflare Workers
1. 打开 [Cloudflare Workers](https://workers.cloudflare.com)。
2. 新建一个 Worker。
3. 将 `worker.js` 内容复制到编辑器。
4. 保存并部署。
5. 访问 `*.workers.dev` 地址并测试 `/works`。

### 方案 B：Cloudflare Pages（Advanced Mode）
1. 从本仓库创建 Pages 项目。
2. 将发布目录设置为 `WebProxy`。
3. 确认 Worker 入口文件为 `WebProxy/_worker.js`。
4. 部署后测试 `/works`。

## 注意事项
- 本项目使用 Module Worker 格式。
- 在 Pages Advanced Mode 中，文件名应为 `_worker.js`（单数）。
- 更新逻辑时请同步维护 `worker.js` 与 `WebProxy/_worker.js` 的行为一致。

## 常见问题
- 部署成功但路由异常：请检查项目根目录与发布目录设置。
- 代理路径返回 400/403：请检查请求参数与 referer 传递逻辑。
- 静态资源加载失败：请检查上游可用性和目标 URL 路径。

## 许可证
本项目基于 **Apache License, Version 2.0** 进行授权。

完整条款见 [LICENSE](LICENSE)，归属声明见 [NOTICE](NOTICE)。
