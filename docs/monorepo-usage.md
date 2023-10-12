# monorepo功能说明
monorepo是一种将多个项目代码存储在一个仓库里的项目管理方式
是一种代码的集中治理的方式
## 包的范围
查看 `pnpm-workspace.yaml` 即可
约定俗称所有的包放在 packages 文件夹下.
## 在根目录安装依赖
```bash
pnpm -w add <依赖名称> 
```
## 在某个目录下安装以来
```bash
pnpm -F @packages/<具体包名>  add  <依赖名称>
```
## 创建新的包
```
cd packages
# 类似 yarn create
pnpm create vite <包名> --template vue-ts
```
## 项目中互相依赖

```
pnpm add @tikkhun/build@* -F @tikkhun/<消费的包>
```
消费的依赖会多一条,将会变成这样
```
 "@advance/build": "workspace:*",
```
