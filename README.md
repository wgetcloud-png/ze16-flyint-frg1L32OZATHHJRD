

# 什么是Sentry？


Sentry本质上是一个服务器端的应用程序，它接收来自客户端（如Web应用程序、移动应用程序或后端服务）的错误日志，然后对这些日志进行聚合、分析和可视化。它提供了详细的错误报告，包括堆栈跟踪、发生错误的上下文（如用户信息、设备信息、环境变量等），以及错误发生的频率和趋势。
# 为什么用Sentry？


1. **实时错误跟踪**：Sentry能够实时捕获应用程序中的错误，并立即通知开发团队。这大大减少了从用户报告问题到开发团队发现并解决问题的时间。
2. **提高应用质量**：通过持续监控和分析错误数据，开发团队可以及时发现并解决潜在的问题，从而提高应用程序的质量和稳定性。
3. **详细的错误报告**：Sentry提供的错误报告非常详细，包括完整的堆栈跟踪和上下文信息。这使得开发人员能够迅速定位问题的根源，并有效地进行调试和修复。
4. **跨平台和语言支持**：Sentry支持多种编程语言和平台，包括JavaScript、Python、Java、Ruby、PHP等。这意味着无论你的应用程序是用什么技术栈构建的，Sentry都能提供有效的错误跟踪服务。
5. **可扩展性和集成性**：Sentry具有强大的可扩展性，可以与各种第三方服务和工具集成，如Slack、GitHub、JIRA等。这使得开发团队能够根据自己的需求定制工作流程，并与其他团队协作工具无缝衔接。
6. **节省时间和资源**：通过自动化错误跟踪和报告，Sentry帮助开发团队节省了大量手动排查问题的时间。这不仅可以提高开发效率，还可以降低维护成本。
7. **用户满意度提升**：及时发现和解决应用程序中的问题可以显著提高用户体验和满意度。当用户遇到问题时，能够快速得到响应和解决，这将增强他们对应用程序的信任和忠诚度。


# 接入方式


Sentry 项目地址：公司私有化部署的 地址
## 准备工作\-项目接入sentry


1. #### 通过域名登录sentry
2. #### 进来后没有看到team信息，加入到组。




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=ZmI2YWJlMDEwYTcxZWNmNmJiZGM3MDY3ZjQ2ZjNiMzZfUG5sYkVKQ2Q3NkV6QmtCZzZtWDZuM2o2U2dCVW5IOXFfVG9rZW46QU02RWI2RHJmb2ZocFN4MmNqUGM2QWwybjZjXzE3MzE2NjI1MDM6MTczMTY2NjEwM19WNA)


3. #### 加入后，进入Projects，查看自己在组内的项目，如果没有的话，需要创建。




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDAxNjNhMWM5YjA4YjgwYzk4ZWFhNWM3NTc4NmNkY2RfUlQ1UVIxek9LaERVR240eU5LQXVRb284d3lpWGdkRlhfVG9rZW46REZUbmIzUnFIbzYzUFB4ZURDSWNFS2dVbkJnXzE3MzE2NjI1MTY6MTczMTY2NjExNl9WNA)


4. #### 创建项目需要权限，如果自己没有权限，可以查看下Members，找有权限的人员帮忙创建




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=N2I3ZjliYzZmMjRmZjQxMDI0NmEyMzk1NWYyMzhjODVfSW8wV2ZRd2VwYWU2TEhSRU1ROEJycERsS09ubzh5MmlfVG9rZW46TkdDc2JYM28xbzRaMFN4TjdGbWNPTDM5bktmXzE3MzE2NjI1Mjg6MTczMTY2NjEyOF9WNA)


5. #### 如下图，直接按照文档说明加入到项目里即可



![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=NzBhY2UwYzc4MzVjMDlhYjQ3ZWZmYjI5MDY5ODU4N2FfSEFnejVRb1lMMktjMURmNjhNZ2NsOU8wY2tmWDltQklfVG9rZW46VVVPMGJsWWl1b0FHZjN4WTNJV2NWaFJNbmZnXzE3MzE2NjI1NTA6MTczMTY2NjE1MF9WNA)


![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=OTkyYWUzMWZmMTAwYWYzMjZiYWMyZDVlZDJjMzBiMWFfdTBhcWZiUHZsalhBOFJhUmtuNGEwd1QyVTltNzNVQ0hfVG9rZW46TEJXcGJTQUFUb1czM3p4RGJWZWNuYTIzbkRjXzE3MzE2NjI1NTU6MTczMTY2NjE1NV9WNA)



6. #### 如果是小程序uni\-app项目，直接使用vue3的sdk无法上报，那么可以使用第三方插件sentry\-miniapp




```
1 import * as Sentry from "sentry-miniapp";
2 Sentry.init({
3   dsn: "https://xxxxxxxxx",
4   // Set tracesSampleRate to 1.0 to capture 100%
5   // of transactions for performance monitoring.
6   // We recommend adjusting this value in production
7   tracesSampleRate: 1.0
8 });
```


 


这样，项目就完成了sentry的接入，项目中有错误会自动上报，可以在sentry的lssues里找到上报的错误。
在sentry后台可以查看上报的的issue，如果觉得不影响的可以点击ignore，这样同样的错误就不会再提示了。
 
## VUE项目的sentry设置


#### sentryInit 伪代码




```
  1 // 调用sentryInit函数进行Sentry的初始化配置
  2 sentryInit({
  3   // 将sentry的init方法和app实例传递给sentryInit
  4   sentry: { init },
  5   app,
  6 
  7   // 指定Sentry项目的DSN（数据源名称），用于将错误数据发送到正确的Sentry项目
  8   dsn: 'https://xxxxx',
  9 
 10   // 配置集成，这里添加了两个集成：BrowserTracing和Replay
 11   integrations: [
 12     // BrowserTracing集成用于跟踪浏览器中的性能问题，如页面加载时间等
 13     new BrowserTracing({
 14       // 通过vueRouterInstrumentation对Vue路由进行追踪
 15       routingInstrumentation: vueRouterInstrumentation(router),
 16     }),
 17     // Replay集成用于记录和回放用户的操作，帮助开发者更好地理解错误发生的上下文
 18     new Replay({
 19       // 配置允许采集的接口，如果有非同源的接口域名需要在这里配置
 20       networkDetailAllowUrls: [window.location.origin],
 21       
 22       // 配置请求头中需要采集的字段 默认只采集 Content-Type、Content-Length、Accept, Authorization 需要确认需不需要
 23       networkRequestHeaders: ['traceparent', '__refreshid__', 'Cookie', 'Authorization'],
 24       
 25       // 配置响应头中需要采集的字段
 26       networkResponseHeaders: ['traceparent', 'set-cookie'],
 27       
 28       // 是否对所有文本进行脱敏处理，这里设置为false
 29       maskAllText: false,
 30       
 31       // 是否对所有输入进行脱敏处理，这里设置为false
 32       maskAllInputs: false,
 33       
 34       // 是否阻止所有媒体加载，这里设置为false
 35       blockAllMedia: false,
 36     }),
 37   ],
 38 
 39   // 设置追踪的采样率，1.0表示100%的追踪事件都会被采集 值介于0 至1.0, 事件是随机挑选的
 40   tracesSampleRate: 1.0,
 41 
 42   // 设置环境变量，用于区分不同的环境（如开发、测试、生产等）
 43   environment: import.meta.env.MODE,
 44 
 45   // 是否开启错误上报，
 46   enabled: true,
 47 
 48   // 设置版本号，可以用来过滤和定位特定版本的错误
 49   release: import.meta.env.BUILD_TIME as string,
 50 
 51   // 配置需要忽略的错误类型或错误消息，这些错误将不会被上报到Sentry
 52   ignoreErrors: [
 53     'ResizeObserver loop limit exceeded',
 54     // ...（其他需要忽略的错误）
 55     // 'ResizeObserver loop completed with undelivered notifications',
 56     // /Failed to fetch dynamically imported module/,
 57     // /Failed to load module script/,
 58     // /Importing a module script failed/,
 59     // /promise rejection captured with keys: code, error, msg/,
 60     // /exception captured with keys: code, data, msg/,
 61     // /Unable to preload CSS for/,
 62     // /exception captured with keys: errorFields, outOfDate, values/,
 63   ],
 64   
 65   initialScope: {
 66     tags: { "my-tag": "my value" },
 67     user: { id: 4222xxx, email: "xxxx.com" },
 68   },
 69 
 70   // 设置用户名
 71   username: xxx.userName,
 72 
 73   // 是否将错误记录到控制台，这里设置为true
 74   logErrors: true,
 75 })
 76 
 77 
 78 
 79 export function configSentryPlugin() {
 80   return vitePluginSentry({
 81         // 指定 Sentry 服务的 URL
 82         url: 'https://sentry.xxxx.cn',
 83     
 84         // 指定 Sentry 的授权令牌，这是连接 Sentry 服务并进行错误追踪的凭证
 85         authToken: '', //sentry授权令牌
 86     
 87         // 指定 Sentry 中的组织名称
 88         org: 'sentry',
 89     
 90         // 指定 Sentry 中的项目名称
 91         project: 'xxxx',
 92     
 93         // 指定发布的版本，这里使用了环境变量 BUILD_TIME 的值作为版本信息
 94         release: process.env.BUILD_TIME as string,
 95     
 96         // 配置 source map 的相关设置，用于在 Sentry 中更准确地定位错误位置
 97         sourceMaps: {
 98           // 指定需要包含进 source map 的文件或文件夹，这里包含了 './dist/assets' 文件夹
 99           include: ['./dist/assets'],
100           
101           // 指定需要忽略的文件或文件夹，这里忽略了 'node_modules' 文件夹
102           ignore: ['node_modules'],
103           
104           // 设置 source map 的 URL 前缀，用于在 Sentry 中构建正确的 source map URL
105           urlPrefix: '~/cloudConfigAssets',
106         },
107     
108         // 设置跳过环境检查，即使在非生产环境中也上传 source map 和错误信息到 Sentry
109         skipEnvironmentCheck: true,
110     })  
111 }
```


在项目中主动上报错误

> 方法: **sentryLog** (主动上传错误.'info')


用途的话: 可以预埋在项目中，比方说项目中接口的catch错误，给自己做一些标识，好定位问题。
 
## 对项目设置企业机器人提醒


1. #### 准备企业微信机器人。


企业微信机器人发送消息的API: https://developer.work.weixin.qq.corm/document/path/91770
2. #### 使用sentry的webhook插件,通知企业微信。




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=NGM1MjBmOGM1M2I3MDUyZWJkYzMzYTRjMjNjMDA2MjRfakpwekhJS25uMFg3ZGptMVViSEtLNHNaU1FZRXFzMEpfVG9rZW46SmVWdGJvNElEb2x1OWJ4UXJidGNZUkhPbklSXzE3MzE2NjI1ODk6MTczMTY2NjE4OV9WNA)


3. #### 点击settings，projects


找到对应的项目，再点击Alert setting，可以在WEBHOOKS的callback urls里添加hooks地址。
如果没有WEBHOOKS这块东西,那可能需要管理员去打开，并填入。在同一个页面的最下面。


![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=MzIyNjY0NDliNzNlYjAwMjcxODFjOGViMDk3NzI2NjVfelU4cDNuSVlCNW5YNEJ3TnhEYVZMRlJPeEdjaXBVNHpfVG9rZW46R2piY2JkYXc3b0pJb1B4SjkySWNZU0tGbmxnXzE3MzE2NjI2MDQ6MTczMTY2NjIwNF9WNA)


 

![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=ODYwZjMxNmM1Y2QxYmU0M2U1MTRmOGM3YzcxMjg5ZTJfVHgyWDZBQzJPSW9TZUVkRHc0WHNMdXFoZ1g1SnREbkdfVG9rZW46QnBEcGJRREh6b3NobHd4bm5ITGNqZmxibnllXzE3MzE2NjI2MDk6MTczMTY2NjIwOV9WNA)


## 对项目配置alert规则


1. #### 进入警报页面




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=NmJiZmVjZWFiYTM1N2M4MTUzODhlYzQ1ZThiZTlmODFfZjJrZXJUUVczb1BzN1BLRlRmV2FXRjBxMTFxdXV3Y2RfVG9rZW46Qk1PV2JBQzgwb3padFB4OGU0NGNRSjdBbjBKXzE3MzE2NjI2MzQ6MTczMTY2NjIzNF9WNA)


2. #### 进入后，选择issues，错误等级，环境等变量，然后可以根据自己的实际情况设置条件和过滤信息。




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDFhYjRkYzlhYWIxN2JmY2Y0YTZhZmZlNzFhZDAxZGVfVkZoekNUUWNMYU5hV3A1NmtheG5ISTRHTkJ1UzZDbVZfVG9rZW46Q09LUmJZNkhob205YUp4RUVwT2NXSVRpbjdlXzE3MzE2NjI2NDE6MTczMTY2NjI0MV9WNA)


## 设置项目的sourceMap


#### 定位错误位置


前端项目的代码都是混淆的。虽然能捕捉到的错误，但我们在控制台没法定位到具体的位置。所以sentry可以上传sourceMap，这样错误就能定位到具体的某一行了。
#### 实现思路


本地代码打包(打包文件中有sourceMap)，然后通过命令或插件上传到sentry服务，sentry再根据release版本匹配到相应的js和map。然后就可以在sentry查看错误的位置了。
(sourceMap上传到sentry，但是不能上传到生产，所以这块在每个项目要处理好。)
1. #### 生成上传的token




![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2MzNzhiODg1NTNkN2YyZWUyZjhmNzEzZGNjNWYxNmZfNGlPT29UdjdiQjMxdWViZmx5TWk1TDhLd2N4cDA4WERfVG9rZW46RFdSWWJwa0ZKbzJwVzh4ckMwS2NZYUk3bnJjXzE3MzE2NjI2NTg6MTczMTY2NjI1OF9WNA)


这里一般要把 project:write和project:releases勾上


![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=MDczNzY1NGEzYTY5NzAyOWZkMmRmYzUxNjcyZDk1NWVfRDU5ZTZkSE5ucHNMVklEaWdEZjltR1hBMjk4bURXZXFfVG9rZW46V3hsMWJLRm1Zb282ck54WnJOeGMxTGtUbktoXzE3MzE2NjI2NzA6MTczMTY2NjI3MF9WNA)


这样就生成了authtoken
2. #### 上传方式


sourceMap上传有2种方式，一种是手动上传，还有一种是通过插件上传（建议使用插件 省事）
##### 使用插件上传


##### webpack


可以安装'@sentry/webpack\-plugin'上传。


```
 1 // vue.config.js
 2 const SentryCliPlugin = require('@sentry/webpack-plugin')
 3 
 4 ...
 5 
 6 configureWebpack(config) {
 7      if (process.env.NODE_ENV === 'production') {
 8           config.plugin('sentry').use(SentryCliPlugin, [{
 9              include: './dist/assets',    // 指定上传目录
10              ignoreFile: '.gitignore',  // 指定忽略文件配置
11              release: process.env.VUE_APP_BASE_API,  // 指定发布版本
12              ignore: ['node_modules', 'webpack.config.js'], 
13              configFile: './.sentryclirc',   // 指定sentry上传配置
14              urlPrefix: '~/assets/'   // 保持与publicpath相符
15         }])
16     }
17 }
```


vite


可以安装 'vite\-plugin\-sentry'



```
 1 import vitePluginSentry from 'vite-plugin-sentry';
 2 
 3 vitePluginSentry({
 4   url: 'https://sentry.xxx.cn',
 5   authToken: 'xxx', // sentry授权令牌
 6   org: 'sentry',
 7   project: 'xxx',
 8   skipEnvironmentCheck: true,
 9   release: process.env.BUILD_TIME as string,
10   sourceMaps: {
11     include: ['./dist/assets'],
12     ignore: ['node_modules'],
13     urlPrefix: `${process.env.VITE_PUBLIC_PATH}/assets`,
14   },
15 }),
16 
17 build: {
18     target: 'es2015',
19     sourcemap: true,
20 },
```



这样，就可以在使用build命令的时候，自动打包上传了
使用命令清空sourceMap文件
sentry\-cli release files xxx delete \-all
 
最后在构建对时候加一条命令,构建完成后删除sourcemap,避免生产环境上有sourcemap
rm ./dist/\*\*/\*.map
 
## 上报方法封装


伪代码




```
 1 /**
 2  * sentry 初始化函数
 3  *
 4  * @param options - sentry 对象
 5  *
 6  * @returns 返回当前的刷新 id
 7  * @public
 8  */
 9 export declare const sentryInit: ({ sentry, app, environment, enabled, release, tracesSampleRate, tags, username, dsn, isMiniapp, integrations, normalizeDepth, beforeSend, ...otherOptions }: SentryOptions) => {
10     __refreshId__: string;
11 };
12 /**
13  * 基础 sentry 上报函数
14  *
15  * @param sentry - sentry 对象
16  * @param error - 错误信息
17  * @param options - 额外的信息
18  *
19  * @returns type and meaning of return value
20  * @public
21  */
22 export declare const sentryLog: (sentry: any, error: Error | string, options: SentryLogOptions) => void;
23 /**
24  *
25  * 记录历史 api 请求信息
26  *
27  * @param apiLog - api 数据
28  * @param maxSaveLength - 最大保存长度
29  *
30  * @returns 无
31  * @public
32  */
33 export declare const saveApiLog: (apiLog: ApiLog, maxSaveLength?: number) => void;
34 /**
35  *  sentry api 接口错误上报函数
36  *
37  * @param sentry - sentry 对象
38  * @param error - 错误信息
39  * @param options - 额外的信息
40  *
41  * @returns 无
42  * @public
43  */
44 export declare const sentryApiLog: (sentry: any, error: Error | string, options: SentryApiLogOptions) => void;
```


 


 



# 扩展


# 录屏精准复现


Sentry 官方对于 sentry 一直处于维护中，官方在 23 年新增了 replay 能力，即支持在用户报错的时候上报用户的操作视频，方便排查问题。
**回放设置**
Sentry 启用回放功能会**默认对所有数据进行脱敏**，包括图片、文字、输入框等等，某些数据**经多方确认不需要脱敏**且可能会影响问题的定位，可以取消脱敏
需要关注的脱敏参数 https://docs.sentry.io/platforms/javascript/guides/vue/session\-replay/configuration/


**block 与 mask 的区别，对于文本内容 block 的字段直接不显示，mask 显示为 \*\*\*；对于媒体元素如 img、****svg** **等 mask 无效果**


```
1 {{ xxx }}
```



```
使用情况
```

1. 默认过滤所有，不需要脱敏的数据增加sentry\-unmask、sentry\-unblock的类或者增加data\-sentry\-unmask、data\-sentry\-unblock的属性取消,适合敏感信息较多的场景
2. 默认所有不过滤，对于需要脱敏的数据增加sentry\-mask、sentry\-block的类或者增加data\-sentry\-mask、data\-sentry\-block的属性，适合敏感信息较少的场景




```
1 // 默认所有数据不脱敏
2 new Replay({
3   networkDetailAllowUrls: [window.location.origin],
4   networkRequestHeaders: ['traceparent', '__refreshid__', 'Cookie'],
5   networkResponseHeaders: ['traceparent', 'set-cookie'],
6   maskAllText: false,
7   maskAllInputs: false,
8   blockAllMedia: false,
9 }),
```


3. 某些场景如dom由第三方依赖生成，无法增加class或者属性，可以统一在全局增加




```
1 new Replay({
2     networkDetailAllowUrls: [window.location.origin],
3     networkRequestHeaders:['traceparent', '_refreshid_', 'set-cookie'],
4     networkResponseHeaders:['traceparent', 'set-cookie'],
5     block:['.mce-content-body'],
6 })
```


## 使用分析


![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=ODJjOGQ1YTFjYmViYzYzNzg2ZTRiN2VkNzJiNTNmOGVfWlRLY25zeEdSTUtFeE5Bck9uQUJjRzlwbnVDTkduVk9fVG9rZW46S0cwYWJOWDVab1lwdVJ4RUo1SWNLMkJibnFmXzE3MzE2NjIyNzQ6MTczMTY2NTg3NF9WNA)
 
整个页面分为三块，左边为用户操作的回放，包括鼠标轨迹；右侧为分析面板，包含页面各种各种时刻的状态，支持点击各类状态将回放跳转到对应时间；下方为进度条，进度条绿点为页面跳转，紫点为点击，红点为报错，方便快速在进度条查看用户的各种操作
 
1. ### Console


![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=NWExZjkyMDJkZWVlMDljNDA3ODRmMjc1NWNiOGIxNmVfT0VHS0FjMkZCRm9xZ25YbHRDeWNvOEw3NFgzQlBJdnZfVG9rZW46WFVQcWJYaGc1b2k1enZ4NTAzR2NWUUJrbjJiXzE3MzE2NjIyNzQ6MTczMTY2NTg3NF9WNA)
2. ### Network


可以查看对应的请求，包括资源和接口，支持查看请求的的 `header` 和`response`，`header`支持默认的`Content-Type`、`Content-LengthAccept`，以及在`networkRequestHeaders` 和 `networkResponseHeaders`中配置的字段
![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=MGJhMzQ1OTM2OWZlNWI3ZTI4ZTlhZWY1MDc5YWFjOGJfMVVxd2tCZlBCM2VGS3FBeWNHSGJLQmJhdXhDOFFROUtfVG9rZW46VHpBM2JqbmZKb2VFUEh4dGNHbmNwelI5bk9jXzE3MzE2NjIyNzQ6MTczMTY2NTg3NF9WNA)
![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=MGU1MDRjNmJmYmQ3OTg0ZjBjMzM4Y2MxY2NlOTRjNWZfbk16QmhZQTdTSnhOM00xVll3RVgxREF0TW9sODBUQTZfVG9rZW46UUl5dGI5UFdHb1kzakh4Y1dpdmNaQTdNbmZlXzE3MzE2NjIyNzQ6MTczMTY2NTg3NF9WNA)
![](https://aivns8zv1q6.feishu.cn/space/api/box/stream/download/asynccode/?code=OTY5OWZmOTE3Y2U1ZGE1MWVlZTU1ODU1YTE3MWQ1OWFfZnZZMExvMW9sbmZ5dTh3ZjZFV3FoTVBCZVZkRTd4a1RfVG9rZW46Q2JSZWJwZ21Pb2prM3p4bTFNYmNCMXcxbmJoXzE3MzE2NjIyNzQ6MTczMTY2NTg3NF9WNA)



 


**剩下的就需要自己坚持主动 或者 团队坚持每双周过一次所有上报的问题，专人持续轮流跟进，常态化治理。为自己及团队的项目保驾护航。**



 本博客参考[樱花宇宙官网](https://yzygzn.com)。转载请注明出处！
