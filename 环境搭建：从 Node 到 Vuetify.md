# 环境搭建：从 Node 到 Vuetify

## Node 与 NPM

1. 下载并安装 Node

2. 创建 node_cache 和 node_global 文件夹

3. NPM 环境变量配置和查看

		$ npm config set prefix "...\node_global"
		$ npm config set cache "...\node_cache"

		$ npm config get prefix
		$ npm config get cache

## 通过 VueCli 创建 Vuetify 3 项目

1. 安装 VueCli 5

		$ npm install -g @vue/cli

2. 创建 Vue 3 项目

		$ vue create [project-name]

3. 添加 Vuetify 3

		$ vue add vuetify

## 其他

- 使用 Vue 官方脚手架创建项目

		$ npm init vue@latest

- 使用 Vite 创建项目

		$ npm create vite [project-name] -- --template vue