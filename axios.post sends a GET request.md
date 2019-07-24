参考 [axios.post but sent a GET request #147](https://github.com/ly525/blog/issues/147)
axios post请求如果url最后没有/，后端django会返回一个301重定向，将其变为get请求，从而产生405错误
