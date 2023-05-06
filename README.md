# chatgpt_commercial
**本项目是基于我的免费开源版本 https://github.com/dirk1983/chatgpt 开发的商业版，同样使用PHP开发，没用任何框架，方便二次开发。**

**和我的免费开源项目相比有以下几项差异：**

| 差异 | 开源版 | 商业版 |
| --- | --- | --- |
| 是否开源 | 完全开源 | 完全开源，支持二开。更新需要绑定域名，不允许转卖 |
| 项目定位 | 个人自用或小范围分享，对服务器资源要求低 | 商业化运营，支持用户付费使用，对服务器资源要求高一些 |
| 问答速度 | stream流模式，session传递问题和上下文，无需数据库，但多人同时使用时可能会卡顿 | stream流模式极速版，更多异常和超时处理机制，数据库传递问题和上下文，多人使用不卡顿 |
| 历史对话 | 不支持用户查看自己的历史对话，仅展示当前对话，管理员可以查看所有用户历史对话 | 用户可以查看自己的所有对话记录，可以切换到任意一个话题的上下文中继续提问 |
| 支持会员 | 不支持 | 支持会员和提供付费业务 |
| API_KEY数量 | 只能配置一个 | 可以配置无数个，自动轮询，自动剔除无效API_KEY |
| 前端界面 | 默认深色背景风格 | 默认浅色背景风格，未来将支持多种风格随意替换 |
| 使用模式 | 只能免费分享给朋友使用，或要求使用者自备API_KEY | 用户可以通过在线支付购买查询次数，或通过淘宝或发卡站购买储值卡使用 |
| 角色和场景 | 支持预设问题，不支持定义角色 | 支持定义角色和针对各场景的预设问题 |
| 画图功能 | 不支持画图功能 | 支持画图功能 |
| 切换模型 | 只能设置单一模型 | 支持多种模型自选 |
| 功能扩展 | 免费使用，用户根据自己需要改进代码，开源版未来没有架构层面修改的计划 | 一次购买永久免费升级，用户可以提需求，商业版会不断改进并持续更新 |

**本项目目前已实现的功能如下：**

1. 无需注册会员，微信扫码登录。由于注册微信有门槛，因此方便用户登录的同时，还可以防止用户批量注册账号白嫖体验次数。还可以给公众号引流。
2. 每个微信用户可以设置成免费体验若干条数。
3. 后台可以设置API_KEY列表，全局+出错时自动轮询，保证用户每次查询都能返回结果。
4. 支持批量生成充值卡，可设置查询次数和有效期。次数和有效期用完之前续费，累加次数并延长有效期。
5. 暂时不支持微信支付或支付宝付费接口，可以生成充值卡后挂到发卡站、淘宝店、微店、扫站长微信二维码转账。
6. 进一步优化接口响应速度，实现秒级回复，并支持查询和继续历史对话。
7. 支持切换模型，支持切换角色，支持画图功能。

**近期功能规划：**

1. 已完成：支持设置跳转到指定的微信服务号获取用户openid（必须是微信认证过的服务号，需要预先配置好环境）
2. 已完成：支持设置PC端访问网站时，手机微信扫码后跳转的地址
3. 支持关联第三方用户一键登录，即在其他系统已登录后可直接带着用户信息过来
4. 支持远程更新
5. 支持设置屏蔽词
6. 支持微信支付，支持用户自行扫码购买查询次数，不用再通过充值卡充值

**中长期功能规划：**
1. 支持批量查看每个API_KEY的余额等信息，支持二次验证被标记为失效的KEY
2. 如果系统的回答速度超过n秒则本次问答免费
3. 支持多个前端UI风格自由切换
4. 支持支付宝当面付
5. 支持自定义ChatGPT的system_role，对具体使用场景进行效果优化，比如写代码、写文章、翻译等
6. 支持用户分享奖励，即通过用户分享链接每注册一个账户则奖励用户一定查询次数，每付费一个用户则奖励一定比例的查询次数
7. 其他功能需求持续更新中……

**部署要求：**
1. 运行本项目必须要有自己的服务器，虚拟主机+Mysql数据库也可以，我不提供服务器或虚拟主机服务，请各位自行购买。
2. 最好是在海外服务器上部署本项目，比如腾讯云东京轻量，国内服务器访问OpenAI接口的话需要代理或反代。
3. 对CPU没有太高的要求，内存最好不小于1GB，硬盘容量20GB也能用，后期随着问答日志的增加可再考虑扩容。
4. 本项目对性能和带宽消耗极低，对于几百个用户的规模各云主机运营商最低的配置就够用。
5. 内部论坛上已有详细的安装流程和配置文档，部署起来很简单，小白用户也能自己搞定。

**其他说明：**
1. 本商业版网站目前已包含规划好的6点功能，近期规划预计一周内完成，其他功能也将尽快完善。
2. 初步计划定价299元，限量200人，未来随着功能不断完善可能会提升价格，但只要一次购买终身免费升级。
3. 只要是通用需求我会尽快完善免费更新。我的微信群已有3000多群友，都是潜在用户，我有动力用好产品打动他们。
4. 商业版完全开源，支持远程自动更新，更新时只能绑定一个域名。每人允许同时运营两个网站，支持二次开发，可以一个站更新，一个站DIY。
5. 每个购买者可加入内部论坛和微信群，讨论产品，对接资源。圈子氛围融洽，干货满满，机会多多，多个朋友多条路，网站299，朋友值千金。一流产品靠运营。
6. 源码仅限购买者使用，请不要免费分享或转卖本项目源码，否则将永久被拉黑。君子协定，自觉遵守，唯有人品，可立一生。
7. 欢迎大家多多宣传本项目。购买者越多，项目越能良性运营下去，每个人都能持续受益。
8. 测试网址和购买方式请进群获取，每个用户免费提问10次，欢迎测试并提出宝贵意见。



**有购买意愿的朋友请加群咨询，名额有限，欲购从速。之前的群人满200了，懒得加好友单独拉了，有兴趣的进新群吧。**

群内仅限咨询商业版事宜，商人、已购用户、发广告的请不要再加了，谢谢配合。


![商业群二维码](https://user-images.githubusercontent.com/5563148/236249070-968e7bf1-a745-4902-b69c-1835b859fd52.png)






**前台界面截图如下（目前界面比较简单，后续会不断改进，欢迎大家提供好看的前端用来借鉴。）：**

PC端：
![1](https://user-images.githubusercontent.com/5563148/232329428-0388ce16-99a6-4601-9672-dc75105e5a63.png)
![微信截图_20230422184607](https://user-images.githubusercontent.com/5563148/233779493-bdbed91c-497b-41f9-9916-ae1687f03dc2.png)
![微信截图_20230422184536](https://user-images.githubusercontent.com/5563148/233779485-11120a84-4f10-4a17-ab0c-b3bb936309a8.png)
![4](https://user-images.githubusercontent.com/5563148/232328753-a43a353c-a7e0-4991-be4f-5e52639853c5.png)

手机端：
![m1](https://user-images.githubusercontent.com/5563148/232328803-2cc476ad-4ae4-480d-ae54-8c706ba19a17.jpg)
![m2](https://user-images.githubusercontent.com/5563148/232328806-e9b6d916-b921-465f-a427-87bcdf49bbc3.jpg)
![m3](https://user-images.githubusercontent.com/5563148/232328808-92102760-ab3b-40f7-b397-fe9a61eda36e.jpg)
![m4](https://user-images.githubusercontent.com/5563148/232328810-b3684b0b-1687-4f5d-9347-406a38a02689.jpg)
![m5](https://user-images.githubusercontent.com/5563148/232328801-ff8e6cae-3120-4286-9f10-a0bf9739a525.jpg)

后台：
![b1](https://user-images.githubusercontent.com/5563148/232328835-cac61a1d-146a-4194-840f-066a599e9a83.png)
![b2](https://user-images.githubusercontent.com/5563148/232328836-ef739254-7f2a-4dab-a3fc-5e5698484418.png)
![b3](https://user-images.githubusercontent.com/5563148/232328837-c7e86353-e04d-41da-a9d3-17bae3cff137.png)
![b4](https://user-images.githubusercontent.com/5563148/232328838-3150e2e2-7b88-4099-97e8-4b3e15e39db0.png)
![b5](https://user-images.githubusercontent.com/5563148/232328840-2bfa1978-e22a-4492-bf77-38c1b0655820.png)
![b6](https://user-images.githubusercontent.com/5563148/232328842-002d26bb-165c-49db-9a4e-517462298abc.png)
![b7](https://user-images.githubusercontent.com/5563148/232328844-928be3c4-ce89-470a-91c3-6c084cdde849.png)
![b8](https://user-images.githubusercontent.com/5563148/232328846-bdd1f14f-ca21-41f4-8a17-eee7b7735593.png)
![b9](https://user-images.githubusercontent.com/5563148/232328847-786ea909-96e5-4b30-80d3-e586766b90f5.png)
![b10](https://user-images.githubusercontent.com/5563148/232328849-49fe83d5-e3b8-423f-b1b2-d36153344d7b.png)
![b11](https://user-images.githubusercontent.com/5563148/232328851-70c2dfe1-5ed4-496c-a44e-f4e0c5b3cd28.png)
![b12](https://user-images.githubusercontent.com/5563148/232328853-a6884ce6-e0dc-4094-8a28-97f24df6727d.png)

