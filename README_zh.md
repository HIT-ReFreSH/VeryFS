<div  align=center>
    <img src="https://raw.githubusercontent.com/HIT-ReFreSH/VeryFS/main/images/logo.svg" width = 30% height = 30%  />
</div>

# VeryFS

![GitHub](https://img.shields.io/github/license/HIT-ReFreSH/VeryFS?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/HIT-ReFreSH/VeryFS?style=flat-square)
![GitHub repo size](https://img.shields.io/github/repo-size/HIT-ReFreSH/VeryFS?style=flat-square)
![GitHub code size](https://img.shields.io/github/languages/code-size/HIT-ReFreSH/VeryFS?style=flat-square)

[Project Hub](https://github.com/HIT-ReFreSH/VeryFS) | [Call for Contributions](https://github.com/HIT-ReFreSH/VeryFS/blob/main/CALL_FOR_CONTRIBUTIONS.md)

VeryFS 是一个 AI 原生的虚拟文件系统，用于把应用、自动化工具和 AI Agent
连接到不同来源的知识与存储资源。

VeryFS 提供类似 Unix 的命名空间，可以挂载本地目录、Git 仓库、WebDAV
端点、远程 VeryFS 实例和研究资料库。项目采用小核心、可插拔驱动、多语言
客户端和可导出工作区的设计，面向 AI 编程、研究和知识工作流。

## 为什么说 VeryFS 是 AI 原生

传统文件系统主要面向人类操作的应用，而 VeryFS 把 AI Agent 作为文件系统
契约的一等使用者：

- **稳定的工作区视图**：外部工具可以获得可预测的 workspace，而不是适配
  各种应用私有 API。
- **挂载感知的来源信息**：文件可以保留来源 driver、mount path、ETag、版本
  提示和缓存策略，方便 Agent 判断数据来源。
- **能力声明机制**：驱动明确声明 list、stat、read、write、manifest、recent、
  materialize、versioning 等能力，Agent 在操作前即可知道边界。
- **最小权限集成**：用户级挂载、ACL、签名请求、secret reference、远程挂载
  缓存策略都是核心设计的一部分。
- **面向 Agent 的发现能力**：manifest 和 recent 查询可以让 Agent 快速理解
  大型工作区，而不是盲目递归扫描所有来源。
- **数据安全优先**：缓存、版本和 retention 设计优先保护用户数据，早期版本
  可以接受更高的存储占用。

## 仓库索引

| 仓库 | 用途 |
| --- | --- |
| `VeryFS.Core` | Core 库、元数据存储、ACL、虚拟命名空间、本地驱动和驱动抽象。 |
| `VeryFS.Server` | VeryFS 的 ASP.NET Core HTTP 服务和 Docker 打包。 |
| `VeryFS.Drivers` | Git、WebDAV、Zotero、远程 VeryFS 以及共享驱动工具包。 |
| `VeryFS.Clients.CSharp` | C# SDK。 |
| `VeryFS.Clients.Python` | Python SDK。 |
| `VeryFS.Clients.TypeScript` | TypeScript SDK。 |
| `VeryFS` | 项目介绍、路线图、贡献指南和仓库索引。 |

本仓库通过 Git submodule 纳入各实现仓库。请使用
`git clone --recurse-submodules https://github.com/HIT-ReFreSH/VeryFS.git`
获取完整源码。

## 当前状态

VeryFS 仍处于 pre-1.0 阶段，API 和驱动契约可能继续调整。当前重点是稳定
核心 API、驱动模型、权限机制、缓存策略和多语言客户端。

## 许可证

VeryFS 使用 MIT License。
