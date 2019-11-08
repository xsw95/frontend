如题，2个依赖版本可能冲突，导致start时报错`cannot find module:'xxx/xxxx/..../webpack.config.dev'`，
react用yarn安装依赖，确保yarn.lock锁定依赖版本，不影响build，才能上线。
