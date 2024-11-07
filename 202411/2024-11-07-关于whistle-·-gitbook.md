# 关于whistle · GitBook
- URL: https://wproxy.org/whistle/
- Added At: 2024-11-07 11:02:58
- [Link To Text](2024-11-07-关于whistle-·-gitbook_raw.md)

## TL;DR
whistle是一款基于Node.js的跨平台web调试代理工具，支持多种匹配和操作协议，通过配置实现HTTP、HTTPS、Websocket请求和响应的查看与修改，功能丰富且易于扩展。

## Summary
1. **whistle简介**：
   - whistle是一个基于Node.js实现的跨平台web调试代理工具，类似于Windows平台上的Fiddler。
   - 主要用于查看、修改HTTP、HTTPS、Websocket的请求和响应。
   - 也可以作为HTTP代理服务器使用。
   - 不同于Fiddler通过断点修改请求响应的方式，whistle采用类似配置系统hosts的方式，一切操作都可以通过配置实现。

2. **功能特点**：
   - 支持域名、路径、正则表达式、通配符、通配路径等多种匹配方式。
   - 可以通过Node模块扩展功能。
   - 所有操作都可以通过配置方式实现，配置格式为`pattern operatorURI`。

3. **匹配方式**：
   - 支持多种匹配方式，如域名匹配、路径匹配、正则匹配、通配符匹配等。
   - 示例：
     ```
     # 域名匹配
     www.example.com
     # 路径匹配
     www.example.com/test
     # 正则匹配
     /^https?://www\.example\.com\/test/(.*)/ referer://http://www.test.com/$1
     ```

4. **操作协议**：
   - 操作协议由操作协议+操作值组成，如`host://opValue`、`file://opValue`。
   - 示例：
     ```
     # 设置请求服务器IP--host协议
     pattern host://127.0.0.1:6666
     # 本地替换--file协议
     pattern file:///User/test/dirOrFile
     ```

5. **配置方式**：
   - `pattern`和`operatorURI`在多数情况下位置可以调换，且支持组合模式。
   - 具体参见：[配置方式](https://wproxy.org/whistle/mode.html)

6. **帮助文档**：
   - **安装启动**：[安装启动](https://wproxy.org/whistle/install.html)
   - **命令行操作**：[命令行操作](https://wproxy.org/whistle/cli.html)
   - **手动更新**：[手动更新](https://wproxy.org/whistle/update.html)
   - **快速上手**：[快速上手](https://wproxy.org/whistle/quickstart.html)
   - **配置方式**：[配置方式](https://wproxy.org/whistle/mode.html)
   - **匹配方式**：[匹配方式](https://wproxy.org/whistle/pattern.html)
   - **操作值**：[操作值](https://wproxy.org/whistle/data.html)
   - **常用功能**：[常用功能](https://wproxy.org/whistle/frequet.html)
   - **插件开发**：[插件开发](https://wproxy.org/whistle/plugins.html)
   - **注意事项**：[注意事项](https://wproxy.org/whistle/attention.html)
   - **常见问题**：[常见问题](https://wproxy.org/whistle/questions.html)
   - **界面功能**：[界面功能](https://wproxy.org/whistle/webui/)
   - **协议列表**：[协议列表](https://wproxy.org/whistle/rules/)
   - **用户反馈**：[用户反馈](https://wproxy.org/whistle/feedback.html)

7. **界面功能**：
   - **Network**：[Network](https://wproxy.org/whistle/webui/network.html)
   - **Composer**：[Composer](https://wproxy.org/whistle/webui/composer.html)
   - **Log**：[Log](https://wproxy.org/whistle/webui/log.html)
   - **Rules**：[Rules](https://wproxy.org/whistle/webui/rules.html)
   - **Values**：[Values](https://wproxy.org/whistle/webui/values.html)
   - **Plugins**：[Plugins](https://wproxy.org/whistle/webui/plugins.html)
   - **WebSocket**：[WebSocket](https://wproxy.org/whistle/webui/websocket.html)
   - **Filter**：[Filter](https://wproxy.org/whistle/webui/filter.html)
   - **Settings**：[Settings](https://wproxy.org/whistle/webui/settings.html)
   - **Weinre**：[Weinre](https://wproxy.org/whistle/webui/weinre.html)
   - **Https**：[Https](https://wproxy.org/whistle/webui/https.html)
   - **Online**：[Online](https://wproxy.org/whistle/webui/online.html)
   - **Mock**：[Mock](https://wproxy.org/whistle/webui/mock.html)

8. **协议列表**：
   - **@**：[@](https://wproxy.org/whistle/rules/@.html)
   - **host**：[host](https://wproxy.org/whistle/rules/host.html)
   - **rule**：
     - **请求替换**：[请求替换](https://wproxy.org/whistle/rules/rule/replace.html)
     - **file**：[file](https://wproxy.org/whistle/rules/rule/file.html)
     - **xfile**：[xfile](https://wproxy.org/whistle/rules/rule/xfile.html)
     - **tpl**：[tpl](https://wproxy.org/whistle/rules/rule/tpl.html)
     - **xtpl**：[xtpl](https://wproxy.org/whistle/rules/rule/xtpl.html)
     - **rawfile**：[rawfile](https://wproxy.org/whistle/rules/rule/rawfile.html)
     - **xrawfile**：[xrawfile](https://wproxy.org/whistle/rules/rule/xrawfile.html)
     - **redirect**：[redirect](https://wproxy.org/whistle/rules/rule/redirect.html)
     - **locationHref**：[locationHref](https://wproxy.org/whistle/rules/rule/locationHref.html)
     - **statusCode**：[statusCode](https://wproxy.org/whistle/rules/rule/statusCode.html)
     - **自定义**：[自定义](https://wproxy.org/whistle/rules/rule/custom.html)
   - **style**：[style](https://wproxy.org/whistle/rules/style.html)
   - **pipe**：[pipe](https://wproxy.org/whistle/rules/pipe.html)
   - **plugin**：[plugin](https://wproxy.org/whistle/rules/plugin.html)
   - **weinre**：[weinre](https://wproxy.org/whistle/rules/weinre.html)
   - **log**：[log](https://wproxy.org/whistle/rules/log.html)
   - **proxy(http-proxy)**：[proxy(http-proxy)](https://wproxy.org/whistle/rules/proxy.html)
   - **https-proxy**：[https-proxy](https://wproxy.org/whistle/rules/https-proxy.html)
   - **socks**：[socks](https://wproxy.org/whistle/rules/socks.html)
   - **pac**：[pac](https://wproxy.org/whistle/rules/pac.html)
   - **filter (excludeFilter | includeFilter)**：[filter (excludeFilter | includeFilter)](https://wproxy.org/whistle/rules/filter.html)
   - **ignore**：[ignore](https://wproxy.org/whistle/rules/ignore.html)
   - **enable**：[enable](https://wproxy.org/whistle/rules/enable.html)
   - **disable**：[disable](https://wproxy.org/whistle/rules/disable.html)
   - **delete**：[delete](https://wproxy.org/whistle/rules/delete.html)
   - **urlParams**：[urlParams](https://wproxy.org/whistle/rules/urlParams.html)
   - **pathReplace**：[pathReplace](https://wproxy.org/whistle/rules/pathReplace.html)
   - **method**：[method](https://wproxy.org/whistle/rules/method.html)
   - **replaceStatus**：[replaceStatus](https://wproxy.org/whistle/rules/replaceStatus.html)
   - **referer**：[referer](https://wproxy.org/whistle/rules/referer.html)
   - **auth**：[auth](https://wproxy.org/whistle/rules/auth.html)
   - **ua**：[ua](https://wproxy.org/whistle/rules/ua.html)
   - **cache**：[cache](https://wproxy.org/whistle/rules/cache.html)
   - **attachment**：[attachment](https://wproxy.org/whistle/rules/attachment.html)
   - **forwardedFor**：[forwardedFor](https://wproxy.org/whistle/rules/forwardedFor.html)
   - **responseFor**：[responseFor](https://wproxy.org/whistle/rules/responseFor.html)
   - **reqMerge**：[reqMerge](https://wproxy.org/whistle/rules/reqMerge.html)
   - **resMerge**：[resMerge](https://wproxy.org/whistle/rules/resMerge.html)
   - **reqScript (reqRules)**：[reqScript (reqRules)](https://wproxy.org/whistle/rules/reqScript.html)
   - **resScript (resRules)**：[resScript (resRules)](https://wproxy.org/whistle/rules/resScript.html)
   - **reqDelay**：[reqDelay](https://wproxy.org/whistle/rules/reqDelay.html)
   - **resDelay**：[resDelay](https://wproxy.org/whistle/rules/resDelay.html)
   - **reqSpeed**：[reqSpeed](https://wproxy.org/whistle/rules/reqSpeed.html)
   - **resSpeed**：[resSpeed](https://wproxy.org/whistle/rules/resSpeed.html)
   - **reqType**：[reqType](https://wproxy.org/whistle/rules/reqType.html)
   - **resType**：[resType](https://wproxy.org/whistle/rules/resType.html)
   - **reqCharset**：[reqCharset](https://wproxy.org/whistle/rules/reqCharset.html)
   - **resCharset**：[resCharset](https://wproxy.org/whistle/rules/resCharset.html)
   - **reqCookies**：[reqCookies](https://wproxy.org/whistle/rules/reqCookies.html)
   - **resCookies**：[resCookies](https://wproxy.org/whistle/rules/resCookies.html)
   - **reqCors**：[reqCors](https://wproxy.org/whistle/rules/reqCors.html)
   - **resCors**：[resCors](https://wproxy.org/whistle/rules/resCors.html)
   - **reqHeaders**：[reqHeaders](https://wproxy.org/whistle/rules/reqHeaders.html)
   - **resHeaders**：[resHeaders](https://wproxy.org/whistle/rules/resHeaders.html)
   - **trailers**：[trailers](https://wproxy.org/whistle/rules/trailers.html)
   - **reqPrepend**：[reqPrepend](https://wproxy.org/whistle/rules/reqPrepend.html)
   - **resPrepend**：[resPrepend](https://wproxy.org/whistle/rules/resPrepend.html)
   - **reqBody**：[reqBody](https://wproxy.org/whistle/rules/reqBody.html)
   - **resBody**：[resBody](https://wproxy.org/whistle/rules/resBody.html)
   - **reqAppend**：[reqAppend](https://wproxy.org/whistle/rules/reqAppend.html)
   - **resAppend**：[resAppend](https://wproxy.org/whistle/rules/resAppend.html)
   - **headerReplace**：[headerReplace](https://wproxy.org/whistle/rules/headerReplace.html)
   - **reqReplace**：[reqReplace](https://wproxy.org/whistle/rules/reqReplace.html)
   - **resReplace**：[resReplace](https://wproxy.org/whistle/rules/resReplace.html)
   - **htmlPrepend**：[htmlPrepend](https://wproxy.org/whistle/rules/htmlPrepend.html)
   - **cssPrepend**：[cssPrepend](https://wproxy.org/whistle/rules/cssPrepend.html)
   - **jsPrepend**：[jsPrepend](https://wproxy.org/whistle/rules/jsPrepend.html)
   - **htmlBody**：[htmlBody](https://wproxy.org/whistle/rules/htmlBody.html)
   - **cssBody**：[cssBody](https://wproxy.org/whistle/rules/cssBody.html)
   - **jsBody**：[jsBody](https://wproxy.org/whistle/rules/jsBody.html)
   - **htmlAppend**：[htmlAppend](https://wproxy.org/whistle/rules/htmlAppend.html)
   - **cssAppend**：[cssAppend](https://wproxy.org/whistle/rules/cssAppend.html)
   - **jsAppend**：[jsAppend](https://wproxy.org/whistle/rules/jsAppend.html)
   - **reqWrite**：[reqWrite](https://wproxy.org/whistle/rules/reqWrite.html)
   - **resWrite**：[resWrite](https://wproxy.org/whistle/rules/resWrite.html)
   - **reqWriteRaw**：[reqWriteRaw](https://wproxy.org/whistle/rules/reqWriteRaw.html)
   - **resWriteRaw**：[resWriteRaw](https://wproxy.org/whistle/rules/resWriteRaw.html)
   - **cipher**：[cipher](https://wproxy.org/whistle/rules/cipher.html)

9. **用户反馈**：
   - [用户反馈](https://wproxy.org/whistle/feedback.html)

10. **License**：
    - [MIT](https://github.com/avwo/whistle/blob/master/LICENSE)
    - [浙ICP备15019507号-2](https://beian.miit.gov.cn/)
