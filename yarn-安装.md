##### 全局安装yarn

```markdown
npm install -g yarn
```

##### 查看yarn版本

```markdown
yarn -v
```

##### 切换淘宝镜像

```markdown
yarn config set registry https://registry.npm.taobao.org -g
```

##### yarn配置项

```markdown
yarn config list // 显示所有配置项 比如yarn的
yarn config get <key> //显示某配置项
yarn config delete <key> //删除某配置项
yarn config set <key> <value> [-g|--global] //设置配置项
```



VS code无法使用

```
在windows搜索windows PowerSell，然后以管理员身份运行ISE
执行命令 set-ExecutionPolicy RemoteSigned
```

