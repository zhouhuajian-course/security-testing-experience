# 安全测试

## 安全测试工具

Burp Suite     
OWASP ZAP  
AppScan  
Xray  
...

## SAST & DAST

Static application security testing (SAST) and dynamic application security testing (DAST) 

/sæst/ /dæst/

静态应用程序安全测试 动态应用安全测试  
白盒测试             黑盒测试  

<table width="100%">
    <tbody>
        <tr>
            <td width="50%">
                <h3>SAST</h3>
            </td>
            <td width="50%">
                <h3>DAST</h3>
            </td>
        </tr>
        <tr>
            <td>
                <p><b>White box security testing</b></p>
                <p>The tester has access to the underlying framework, design, and implementation. The application is tested from the inside out. This type of testing represents the developer approach.</p>
            </td>
            <td>
                <p><b>Black box security testing</b></p>
                <p>The tester has no knowledge of the technologies or frameworks that the application is built on. The application is tested from the outside in. This type of testing represents the hacker approach.</p>
            </td>
        </tr>
        <tr>
            <td>
                <p><b>Requires source code</b></p>
                <p>SAST doesn’t require a deployed application. It analyzes the source code and related dependencies without executing the application.</p>
            </td>
            <td>
                <p><b>Requires a running application</b></p>
                <p>DAST doesn’t require source code or binaries. It analyzes by executing the application.</p>
            </td>
        </tr>
        <tr>
            <td>
                <p><b>Finds vulnerabilities earlier in the SDLC</b></p>
                <p>Scans can be run at various stages of the development process, including in the IDE, when codeVulnerabilities can be discovered at the end of the development cycle or in production.</p>
            </td>
            <td>
                <p><b>Finds vulnerabilities toward the end of the SDLC</b></p>
                <p>Vulnerabilities can be discovered at the end of the development cycle or in production.</p>
            </td>
        </tr>
        <tr>
            <td>
                <p><b>Less expensive to fix vulnerabilities</b></p>
                <p>Since vulnerabilities are found earlier in the SDLC, it’s easier and faster to remediate them. Most issues can be identified and fixed before the code reaches QA.</p>
            </td>
            <td>
                <p><b>Can be more expensive to fix vulnerabilities</b></p>
                <p>Since vulnerabilities are found toward the end of the SDLC, remediation often gets pushed into the next cycle. Critical vulnerabilities may be fixed as an emergency release. With solutions like fAST Dynamic, costs can be easily reduced.</p>
            </td>
        </tr>
        <tr>
            <td>
                <p><b>Can’t discover run-time and environment-related issues</b></p>
                <p>Since SAST tools scan static code, they don’t have visibility into potential runtime vulnerabilities.</p>
            </td>
            <td>
                <p><b>Can discover run-time and environment-related issues</b></p>
                <p>Since the tool uses dynamic analysis, it is able to find runtime vulnerabilities.</p>
            </td>
        </tr>
    </tbody>
</table>

https://www.synopsys.com/blogs/software-security/sast-vs-dast-difference.html

## 漏洞类型列表

<table>
    <tbody>
        <tr>
            <th>序号</th>
            <th>漏洞类型名称</th>
            <th>漏洞数量</th>
        </tr>
        <tr>
            <td>1</td>
            <td><a>SQL注射漏洞</a></td>
            <td><a>27768</a></td>
        </tr>
        <tr>
            <td>2</td>
            <td><a>设计缺陷/逻辑错误</a></td>
            <td><a>7507</a></td>
        </tr>
        <tr>
            <td>3</td>
            <td><a>命令执行</a></td>
            <td><a>6835</a></td>
        </tr>
        <tr>
            <td>4</td>
            <td><a>xss跨站脚本攻击</a></td>
            <td><a>6384</a></td>
        </tr>
        <tr>
            <td>5</td>
            <td><a>后台弱口令</a></td>
            <td><a>5175</a></td>
        </tr>
        <tr>
            <td>6</td>
            <td><a>未授权访问/权限绕过</a></td>
            <td><a>4739</a></td>
        </tr>
        <tr>
            <td>7</td>
            <td><a>敏感信息泄露</a></td>
            <td><a>3587</a></td>
        </tr>
        <tr>
            <td>8</td>
            <td><a>系统/服务运维配置不当</a></td>
            <td><a>2903</a></td>
        </tr>
        <tr>
            <td>9</td>
            <td><a>文件上传导致任意代码执行</a></td>
            <td><a>2713</a></td>
        </tr>
        <tr>
            <td>10</td>
            <td><a>成功的入侵事件</a></td>
            <td><a>2339</a></td>
        </tr>
        <tr>
            <td>11</td>
            <td><a>重要敏感信息泄露</a></td>
            <td><a>2199</a></td>
        </tr>
        <tr>
            <td>12</td>
            <td><a>服务弱口令</a></td>
            <td><a>1921</a></td>
        </tr>
        <tr>
            <td>13</td>
            <td><a>任意文件遍历/下载</a></td>
            <td><a>1859</a></td>
        </tr>
        <tr>
            <td>14</td>
            <td><a>系统/服务补丁不及时</a></td>
            <td><a>1616</a></td>
        </tr>
        <tr>
            <td>15</td>
            <td><a>账户体系控制不严</a></td>
            <td><a>1276</a></td>
        </tr>
        <tr>
            <td>16</td>
            <td><a>应用配置错误</a></td>
            <td><a>907</a></td>
        </tr>
        <tr>
            <td>17</td>
            <td><a>CSRF</a></td>
            <td><a>848</a></td>
        </tr>
        <tr>
            <td>18</td>
            <td><a>网络设计缺陷/逻辑错误</a></td>
            <td><a>805</a></td>
        </tr>
        <tr>
            <td>19</td>
            <td><a>基础设施弱口令</a></td>
            <td><a>733</a></td>
        </tr>
        <tr>
            <td>20</td>
            <td><a>设计错误/逻辑缺陷</a></td>
            <td><a>729</a></td>
        </tr>
        <tr>
            <td>21</td>
            <td><a>用户资料大量泄漏</a></td>
            <td><a>656</a></td>
        </tr>
        <tr>
            <td>22</td>
            <td><a>内部绝密信息泄漏</a></td>
            <td><a>469</a></td>
        </tr>
        <tr>
            <td>23</td>
            <td><a>远程代码执行</a></td>
            <td><a>459</a></td>
        </tr>
        <tr>
            <td>24</td>
            <td><a>网络敏感信息泄漏</a></td>
            <td><a>445</a></td>
        </tr>
        <tr>
            <td>25</td>
            <td><a>XSS 跨站脚本攻击</a></td>
            <td><a>384</a></td>
        </tr>
        <tr>
            <td>26</td>
            <td><a>非授权访问/权限绕过</a></td>
            <td><a>369</a></td>
        </tr>
        <tr>
            <td>27</td>
            <td><a>文件包含</a></td>
            <td><a>331</a></td>
        </tr>
        <tr>
            <td>28</td>
            <td><a>拒绝服务</a></td>
            <td><a>284</a></td>
        </tr>
        <tr>
            <td>29</td>
            <td><a>非授权访问/认证绕过</a></td>
            <td><a>272</a></td>
        </tr>
        <tr>
            <td>30</td>
            <td><a>默认配置不当</a></td>
            <td><a>269</a></td>
        </tr>
    </tbody>
</table>

## 安全漏洞类型

缓冲区溢出、跨站脚本、DOS攻击、扫描、SQL注入、木马后门、病毒蠕虫、web攻击、僵尸网络、跨站请求伪造、文件包含、文件读取、目录遍历攻击、敏感信息泄露、暴力破解、代码执行漏洞、命令执行、弱口令、上传漏洞利用、webshell利用、配置不当/错误、逻辑/涉及错误、非授权访问/权限绕过、URL跳转、协议异常、网络钓鱼、恶意广告、网络欺骗、间谍软件、浏览器劫持、键盘记录、窃密木马、端口扫描、黑市工具、电子邮件、电脑病毒、网络蠕虫、文件下载、权限许可和访问控制、webshell上传

## 漏洞分类 

<table>
    <tbody>
        <tr>
            <td>HTTP 参数污染</td>
            <td>SSI 注入</td>
            <td>登录绕过</td>
        </tr>
        <tr>
            <td>后门</td>
            <td>内存溢出</td>
            <td>目录穿越</td>
        </tr>
        <tr>
            <td>Cookie 验证错误</td>
            <td>整数溢出</td>
            <td>解析错误</td>
        </tr>
        <tr>
            <td>跨站请求伪造</td>
            <td>HTTP 响应伪造</td>
            <td>越权访问</td>
        </tr>
        <tr>
            <td>ShellCode</td>
            <td>HTTP 请求伪造</td>
            <td>跨站脚本</td>
        </tr>
        <tr>
            <td>SQL 注入</td>
            <td>内容欺骗</td>
            <td>路径泄漏</td>
        </tr>
        <tr>
            <td>任意文件下载</td>
            <td>XQuery 注入</td>
            <td>代码执行</td>
        </tr>
        <tr>
            <td>任意文件创建</td>
            <td>缓存区过读</td>
            <td>远程密码修改</td>
        </tr>
        <tr>
            <td>任意文件删除</td>
            <td>暴力破解</td>
            <td>远程溢出</td>
        </tr>
        <tr>
            <td>任意文件读取</td>
            <td>LDAP 注入</td>
            <td>目录遍历</td>
        </tr>
        <tr>
            <td>其他类型</td>
            <td>安全模式绕过</td>
            <td>空字节注入</td>
        </tr>
        <tr>
            <td>变量覆盖</td>
            <td>备份文件发现</td>
            <td>中间人攻击</td>
        </tr>
        <tr>
            <td>命令执行</td>
            <td>XPath 注入</td>
            <td>格式化字符串</td>
        </tr>
        <tr>
            <td>嵌入恶意代码</td>
            <td>URL 重定向</td>
            <td>缓冲区溢出</td>
        </tr>
        <tr>
            <td>弱密码</td>
            <td>代码泄漏</td>
            <td>HTTP 请求拆分</td>
        </tr>
        <tr>
            <td>拒绝服务</td>
            <td>释放后重用</td>
            <td>CRLF 注入</td>
        </tr>
        <tr>
            <td>数据库发现</td>
            <td>DNS 劫持</td>
            <td>XML 注入</td>
        </tr>
        <tr>
            <td>文件上传</td>
            <td>错误的输入验证</td>
            <td>本地文件包含</td>
        </tr>
        <tr>
            <td>远程文件包含</td>
            <td>通用跨站脚本</td>
            <td>证书预测</td>
        </tr>
        <tr>
            <td>本地溢出</td>
            <td>服务器端请求伪造</td>
            <td>HTTP 响应拆分</td>
        </tr>
        <tr>
            <td>权限提升</td>
            <td>跨域漏洞</td>
            <td>错误的证书验证</td>
        </tr>
        <tr>
            <td>信息泄漏</td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>

## 信息安全技术 网络安全漏洞分类分级指南

信息安全技术 网络安全漏洞分类分级指南 GB/T 30279-2020
