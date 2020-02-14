Requests库7个主要方法
requests.request() 基础方法
requests.get()
requests.head()
requests.post()
requests.put()
requests.patch()
requests.delete()


Response对象的属性
r=requests.get(url)
Response对象属性
r.status_code http请求的返回状态，200表示连接成功，404表示失败（不是200都是失败）
r.text        http响应内容的字符串形式，即url对应的页面内容
r.encoding    从http header中猜测的响应内容编码方式  （如果header中不存在charest，则认为编码为ISO-8859-1，这样的编码不能解析中文）
r.apparent_encoding 从内容中分析出的响应内容编码方式（备选编码方式）  （比r.encoding更加准确，更准确的解码，可以将其赋值给r.encoding）
r.content     http响应内容的二进制形式


Requests库异常
requests.ConnectionError    网络连接错误异常，如DNS查询失败，拒绝连接
requests.HTTPError          HTTP错误异常
requests.URLRequired        URL缺失异常
requests.TooManyRedirects   超过最大重定向次数，产生重定向异常   （对一些复杂链接进行访问时）
requests.ConnectTimeout     连接远程服务器超时异常         （与远程服务器链接这一步骤产生的异常）
requests.Timeout            请求URL超时，产生超时异常      （发出URL请求到获得内容整个内容的超时异常）
r.raise_for_status()        如果不是200，产生异常requests.HTTPError



















