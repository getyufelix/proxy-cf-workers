# Proxy CF Workers

`proxy-cf-workers` 是一个基于 Cloudflare Workers 的轻量级反向代理工具。它允许你将请求动态代理到指定的目标地址，并通过环境变量灵活配置目标主机名、端口和协议。该项目非常适合用于快速搭建代理服务，支持 HTTPS 和 HTTP 协议。

## 功能特性

- **动态代理**：通过环境变量配置目标地址，支持动态修改。
- **灵活配置**：支持配置目标主机名、端口和协议。
- **高性能**：基于 Cloudflare Workers 的边缘计算，提供低延迟的代理服务。
- **易于部署**：一键部署到 Cloudflare Workers，无需额外服务器。

## 🚀 部署方式

- **Workers** 部署：复制 [_worker.js](https://github.com/getyufelix/proxy-cf-workers/blob/main/_worker.js) 代码，`保存并部署`即可

## 🔧 环境变量

以下是支持的环境变量及其默认值：

| 变量名           | 描述                            | 默认值     |
| ---------------- | ------------------------------- | ---------- |
| `PROXY_HOST`     | 目标主机名                      | `''`       |
| `PROXY_PORT`     | 目标端口                        | `''`       |
| `PROXY_PROTOCOL` | 目标协议（`http:` 或 `https:`） | `'https:'` |

## 示例场景

### 场景 1：代理到 HTTPS 目标
- 目标地址：`https://api.example.com`
- 配置：

  ```toml
  [vars]
  PROXY_HOST = "example.com"
  PROXY_PORT = ""         # 使用默认端口 443
  PROXY_PROTOCOL = "https:"
  ```

### 场景 2：代理到 HTTP 目标
- 目标地址：`http://localhost:8080`
- 配置：

  ```toml
  [vars]
  PROXY_HOST = "api.example.com"
  PROXY_PORT = "8080"
  PROXY_PROTOCOL = "http:"
  ```

## 许可证

本项目基于 [MIT 许可证](LICENSE) 开源。

感谢使用 `proxy-cf-workers`！🚀
