# HtppRequest
常用python，发现python的request很好用，简单实用。一转到java，发现还是内嵌太多了。简单的将原来繁琐的步骤封装了下。
怎么用
setp 1:
下载apache jar包
setp 2:
在java项目中新建一个libs，将jar复制进去
setp 3:
导入 Bsmali4Get,Bsmali4Post即可。

使用demo
http　get协议
Bsmali4Get httpGet = new Bsmali4Get(
				"http://www.baidu.com");
		httpGet.doGet();//发送请求
		System.out.println(httpGet.getResStatus());//打印响应状态
		System.out.println(httpGet.getResLen());//打印响应长度
		System.out.println(httpGet.getResContent());//打印响应内容
		for (Header header : httpGet.getResHeaders()) {
			System.out.println(header.getName() + ":" + header.getValue());//打印响应http头
		}
    
 http post协议
 
 Bsmali4Post httpPost = new Bsmali4Post(
				"http://web.sycsec.com:80/a2274e0e500459f7/login.php");
		httpPost.addHeader("Accept-Encoding", "identity");//添加http请求头
		httpPost.addData("username", "admin' xor sleep(1)#");//添加post请求数据
		httpPost.addData("password", "x");//添加post请求数据
		httpPost.addData("debug", "1");//添加post请求数据
		httpPost.doPost();
		System.out.println(httpPost.getResStatus());//打印响应状态
		System.out.println(httpPost.getResLen());//打印响应长度
		System.out.println(httpPost.getResContent());//打印响应内容
		for (Header header : httpPost.getResHeaders()) {
			System.out.println(header.getName() + ":" + header.getValue());//打印响应http头
		}
