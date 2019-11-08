# npm,cnpm,yarn
网络原因，给npm,yarn安装淘宝镜像，加速安装依赖

## 获取yarn源
```
yarn config get registry
// https://registry.yarnpkg.com
```

## 配置yarn源
```
yarn config set registry 'https://registry.npm.taobao.org'
// yarn config v0.15.0
// success Set "registry" to "https://registry.npm.taobao.org".
// Done in 0.04s.
```

## npm同理
`npm config set registry=https://registry.npm.taobao.org`

## 下载cnpm
`npm install -g cnpm –registry=https://registry.npm.taobao.org`
