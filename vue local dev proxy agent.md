# vue本地开发代理
在vue项目中，在本地使用proxy代理的时候，经常会发生请求线上接口timeout的问题，原因是vue的代理没有成功科学上网，需要添加agent来实现，例如：
```
'use strict'

const path = require('path')
const ProxyAgent = require('proxy-agent')

module.exports = {
  dev: {

    // Paths
    assetsSubDirectory: 'dsp-static',
    assetsPublicPath: '/',
    proxyTable: {
      '/dsp-web2': {
        agent: new ProxyAgent('socks5://127.0.0.1:1086'), //代理到本地的代理
        target: 'http://dsp.webeyemob.com/',
        // target: 'http://10.30.11.249:8088/',
        // target: 'http://35.245.77.191:3000',
        changeOrigin: true,
      },
      '/dsp-web': {
        target: 'http://dsp.webeyemob.com/',
        // target: 'http://dsp.adjucai.com/',
        changeOrigin: true,
      },
    },
    // Various Dev Server settings
    host: '127.0.0.1', // can be overwritten by process.env.HOST
    port: 9527, // can be overwritten by process.env.PORT, if port is in use, a free one will be determined
    autoOpenBrowser: true,
    errorOverlay: true,
    notifyOnErrors: true,
    poll: false, // https://webpack.js.org/configuration/dev-server/#devserver-watchoptions-

    // Use Eslint Loader?
    // If true, your code will be linted during bundling and
    // linting errors and warnings will be shown in the console.
    useEslint: true,
    // If true, eslint errors and warnings will also be shown in the error overlay
    // in the browser.
    showEslintErrorsInOverlay: false,

    /**
     * Source Maps
     */

    // https://webpack.js.org/configuration/devtool/#development
    devtool: 'cheap-module-eval-source-map',

    // If you have problems debugging vue-files in devtools,
    // set this to false - it *may* help
    // https://vue-loader.vuejs.org/en/options.html#cachebusting
    cacheBusting: true,

    cssSourceMap: true,
  },
}
```
