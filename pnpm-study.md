# 1. 常用命令

| 分类       | 命令                             | 作用                                                         | 示例                                    |
| ---------- | -------------------------------- | ------------------------------------------------------------ | --------------------------------------- |
| 环境安装   | `pnpm -v`                        | 查看 pnpm 版本（验证安装）                                   | `pnpm -v`                               |
| 项目初始化 | `pnpm init`                      | 交互式初始化项目，生成 package.json                          | `pnpm init`                             |
|            | `pnpm init -y`                   | 快速初始化，直接生成默认 package.json（无交互）              | `pnpm init -y`                          |
| 包安装     | `pnpm add <pkg>`                 | 安装包到生产依赖（dependencies）                             | `pnpm add axios`                        |
|            | `pnpm add -D <pkg>`              | 安装包到开发依赖（devDependencies）                          | `pnpm add -D eslint`                    |
|            | `pnpm add -g <pkg>`              | 全局安装包                                                   | `pnpm add -g typescript`                |
|            | `pnpm add <pkg>@<version>`       | 安装指定版本的包                                             | `pnpm add react@18.2.0`                 |
|            | `pnpm add <pkg>@latest`          | 安装包的最新版本                                             | `pnpm add vue@latest`                   |
|            | `pnpm install`/`pnpm i`          | 安装 package.json 中所有依赖                                 | `pnpm i`                                |
|            | `pnpm i --frozen-lockfile`       | 严格按 pnpm-lock.yaml 安装（生产环境推荐）                   | `pnpm i --frozen-lockfile`              |
| 包卸载     | `pnpm remove <pkg>`/`pnpm rm`    | 卸载生产依赖                                                 | `pnpm rm axios`                         |
|            | `pnpm remove -D <pkg>`           | 卸载开发依赖                                                 | `pnpm rm -D eslint`                     |
|            | `pnpm remove -g <pkg>`           | 卸载全局包                                                   | `pnpm rm -g typescript`                 |
| 依赖更新   | `pnpm outdated`                  | 查看可更新的依赖包                                           | `pnpm outdated`                         |
|            | `pnpm update <pkg>`/`pnpm up`    | 更新指定包到最新版本                                         | `pnpm up axios`                         |
|            | `pnpm update`/`pnpm up`          | 更新所有依赖到最新版本                                       | `pnpm up`                               |
|            | `pnpm up <pkg>@<version>`        | 更新指定包到指定版本                                         | `pnpm up react@18.3.0`                  |
|            | `pnpm up -D <pkg>`               | 更新开发依赖                                                 | `pnpm up -D eslint`                     |
| 脚本运行   | `pnpm run <script>`              | 运行 package.json 中的自定义脚本（可简写为 `pnpm <script>`） | `pnpm run dev` / `pnpm dev`             |
|            | `pnpm run <s1> && pnpm run <s2>` | 串行运行多个脚本                                             | `pnpm run lint && pnpm run build`       |
|            | `pnpm run <s1> --parallel <s2>`  | 并行运行多个脚本                                             | `pnpm run lint --parallel pnpm run dev` |
| 缓存与清理 | `pnpm store path`                | 查看 pnpm 缓存目录位置                                       | `pnpm store path`                       |
|            | `pnpm store prune`               | 清理 pnpm 缓存（释放磁盘空间）                               | `pnpm store prune`                      |
|            | `pnpm clean`                     | 清除项目的 node_modules 和本地缓存                           | `pnpm clean`                            |
| 依赖查看   | `pnpm list`/`pnpm ls`            | 查看项目已安装的所有依赖包                                   | `pnpm ls`                               |
|            | `pnpm ls <pkg>`                  | 查看指定包的安装版本及依赖关系                               | `pnpm ls axios`                         |
|            | `pnpm info <pkg>`                | 查看指定包的详细信息（版本、依赖、描述等）                   | `pnpm info axios`                       |
| 安全与工具 | `pnpm audit`                     | 检查依赖包的安全漏洞                                         | `pnpm audit`                            |
|            | `pnpm dlx <pkg>`                 | 临时运行包的命令（无需全局安装，类似 npx）                   | `pnpm dlx create-vite my-project`       |
| 帮助       | `pnpm help`                      | 查看 pnpm 所有命令及说明                                     | `pnpm help`                             |
|            | `pnpm help <cmd>`                | 查看指定命令的详细使用说明                                   | `pnpm help add`                         |