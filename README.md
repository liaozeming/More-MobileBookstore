移动书屋（More） 课程项目
	基于 摩拜单车模式的共享书屋。
	基于百度地图的LBS服务以及扫码功能进行共享模式的类比开发。
	利用geoHash对地理位置进行编码，实现区域匹配。
	数据来源 ：豆瓣图书APIV2
	请结合 服务器端使用：https://github.com/yccy1230/More-Mobile-Book-Store-Server-.git

下面是 项目说明文档的内容：

1.	项目背景
    根据“第十三次全国国民阅读调查”显示，中国人均纸质阅读量为4.58本——微信阅读人数过半。报纸和期刊阅读量分别为54.76期(份)和4.91期(份)，电子书阅读量为3.26。	据不完全统计，目前高校中个人纸质书籍的拥有量人均为73.3本，但实际所使用书籍仅为13本，利用率仅为17.7%。纸质书籍的利用率十分低下。
如何让书籍的阅读变得像那些移动平台上的文章一样受欢迎？我们经过类比思考，并通过询问周围的同学的看法，得到了一个结论——假如我们能使纸质书做到随拿随放，想读就读，那么人们的平均阅读就能够得到显著地提升。

2.	项目简介
	基于目前纸质书籍重用率低，书籍购买成本高，废弃书籍空间占用率高等现状，结合时下热门的共享单车模式及互联网+的理念，打造一款移动端的流动书屋系统，用户可以简单的通过扫码完成换书操作，便捷获得所需的书籍，同时加入社交元素，满足多样化的社交需求，通过网络驱动提升书籍重用率和利用率。
	人们可以随时在路口、学校等各个地方的移动书柜里面借书，并等读完后在任意的一个书柜里面还书，想读就读，还书也相当轻松，打破传统的“哪里借哪里还”的借书规矩。而且，每个移动书柜的书的种类都会随着人们的借与还而发生变化，每浏览一个移动书柜，都是一次带来惊喜的旅程。
	同时，用户还可以拥有一个自己的移动书柜，在其中添置一些所不必要的书，只需打开app轻松一扫录入系统，就能够让其他用户得到相应的讯息，在让书籍发挥价值的同时，说不定能让你与他/她来一次完美的邂逅呢？

技术特点	1.功能点
项目运营方式：
初期以用户自行搭建书架录入书籍为书籍主要来源，使得整个流程得以运行，后期可设置公共书架，以解锁书架的方式进行借书。

1)	扫码借书
流动书屋通过1:1等比例兑换积分的方式进行，通过提前录入书架书籍获得积分。
本着便捷用户的理念，我们尽可能简化用户的借书操作流程：
扫描要接的书的ISBN->确认要借的书籍->积分扣除->完成借书。
2)	扫码录书
每个用户拥有一个自有的移动书屋，用户可以自行进行相应的增删改书籍操作，为了方便用户添加书籍到书库，我们以扫码录书的方式进行添加书籍，并通过豆瓣ISBN接口，尽可能多的为用户提供相应的数据，让用户只需要进行性略微的修改即可完成录书操作。
3)	地图上显示固定位置书架和个人移动书架
通过调用百度地图API实现在地图上显示marker标注书架位置，方便用户查看附近的书架，同时点击书架即可进行书架浏览以及书籍预约的方式进行。
4)	书籍预约
用户在浏览书架的过程中总会遇到心意的书籍，又因为各种原因无法马上去借书，因此可以通过预约功能预约书籍，暑假的主人会收到你的消息哦。
5)	个性化消息提醒
用app没兴致？宅在家很无聊？萌妹子要不要？！！！我们有特制的萌妹子消息提醒，只要你的书架上的书够Amazing！借的人足够多！我们就让你听个够！
6)	书籍损坏举报功能
什么？你说有人书架上的书是假的？（拨打12580，一按我帮你！）通过举报功能，我们后台核实后我们帮你解气！
7)	书籍漂流瓶
心仪上次借你书的妹子很久了？害羞又不敢开口？别怕！快看看她喜欢什么书，上架它给她留言表白吧！用户在上架书籍时可对放入书架的书籍进行留言，借书扫码时会跳出这条留言！。
8)	对指定书籍的搜索功能，附近5公里出现时提示（GEOHASH地理位置哈希）
GEOHASH！一个高大上的算法，让你快速匹配到附近5公里的书籍。
9)	豆瓣书评
App提供的信息不全面？想要看看别人的评价？最大的书籍交流平台豆瓣API！就不信没你想看的内容！通过WebView跳转到书籍的
10)	借阅记录查询
想看看是谁借了你的书？或者想看看之前借了什么书？点开历史记录，一看便知！
11)	个人资料维护
想换头像了？想试试表情包？没问题！一键自拍！一键剪裁！有你想要！为你附赠特制高斯模糊背景！

2.技术要点
UI层：
	使用ToolBar替换原有顶栏
	使用DrawableLayout实现主界面
	使用FloatingActionButton（FAB）按钮
	使用多种Material Design（MD）风格控件
	使用CardView优化界面
	登录界面输入法自适应（动态缩放）
	实现列表Item侧滑功能按钮
	使用Fragment实现个性化界面
	使用ListView实现列表展示
	使用RefreshLayout实现列表刷新
	使用WebView对接豆瓣图书API（含进度条）
	调用系统权限，如拍照，拨打电话等
	安卓生命周期运用恰当

数据传输：
	使用SharedPerference存储用户数据
	序列化（Serializable）对象在Activity之间传参
	Intent含参跳转
	自定义Adapter实现（继承BaseAdapter）
	使用AsyncHttp（底层基于HttpCilent）实现异步网络请求
	使用Http协议进行文件的上传头像
	使用Json格式进行前后端数据传输

算法：
	使用geoHash对地理位置进行编码，实现区域匹配
	使用高斯模糊实现头像模糊用作背景图片

第三方支持：
	百度地图LBS服务
	友盟U-Push推送服务
	豆瓣图书API-V2接口服务
	WheelView个性化弹窗选择界面
	QRCode-Androi安卓扫码控件
	ThinkAndroid基本框架支持

服务器支持：
	采用SpringMVC框架
	采用Restful接口
	采用Hibernate持久化数据库的方式
	使用各种SQL语句

3.	项目特色
技术特色：
	利用GEOHASH地理哈希的方式实现附近书籍匹配，提高了检索效率
	运用高斯模糊，将头像作为背景图展示
	调用第三方API（豆瓣、百度地图），优化数据来源

体系特色：
	提供完善的用户交流机制。用户无论是进行书籍上架还是借阅，都能进行留言。用户之间也能方便地进行交流。万一把到爱读书有气质的妹子了呢。
	完善的借书机制，先录入书籍获取积分，然后借书，使用户们形成一个良好的借阅环境。
	与豆瓣书评等联动，提供用户了解更多书籍相关信息的机会。
	UI精美大方，配色简洁凝练，功能直观明了，让用户体验最大舒适化
	相比普通的共享模式，用户具有更高的参与度与粘性。当前流行的共享单车、共享汽车都只是用户单方面使用官方提供的车辆。而在共享书屋的模式中，内容的使用者与提供者都是用户，用户从中体验到分享的乐趣。以此，共享书屋做到了真正的“共享”。

备注	项目开发和部署环境
开发环境：
前端：Android Studio 2.3.3
后台：Myeclipse 2017CI3
JDK：jdk1.8.0_91

部署环境：
服务器：windows server 2008
数据库：MySQL 5.7
Web容器：Tomacat8.5
JDK：jdk1.8.0_91


附录

启动页
启动页使用了淡出效果，通过AlphaAnimation实现，图片为其他app的启动页图片。
 
菜单页
android.support.v4.widget.DrawerLayout以及android.support.design.widget.NavigationView实现侧滑菜单
de.hdodenhof:circleimageview:1.3.0实现顶部的圆形头像
setNavigationItemSelectedListener设置监听跳转
     
首页  
百度地图LBS服务实现地图展示、地图标注、定位服务
FloatingSearchView实现搜索查询功能（GEOHASH附近匹配算法）
FloatingActionButton实现浮动按钮
GeoHash实现分地区搜索功能

个人资料页
头像背景部分使用高斯模糊
性别选项使用wheelview（滚动选择框）
头像上传使用AsyncHttpCilent.post实时上传到服务器
头像更改支持拍照、图片选择、图片裁剪

我的书架页      
FAB实现添加书籍按钮
ToolBar实现右上角菜单栏
SwipeListView+SwipeManager实现ListItem左滑按钮（左滑删除）
SwipeRefreshLayout实现下拉刷新功能
MyRefreshManager解决下拉左滑冲突
 
搜索结果页
RelativeLayout将界面分为上下两部分
BaiduMapView为上半部分界面（含定位）
ListVIew为下半部分界面
提供预约和浏览书架功能
预约时服务器会通过UMeng的pushsdk对相应用户推送通知
浏览书架回跳转到WebView并访问豆瓣图书API查看书籍详细信息及书评
     
扫码借书页    
使用两个Fragment实现上滑界面点即可进入书籍详情界面
同时书籍下面有书籍评分
确认借书后服务器将通过UMeng服务向相应用户发送消息

书籍详情页
书籍详情界面数据使用豆瓣图书APIV2的数据

豆瓣书评页
WebView实现浏览器功能
onProgressChanged监听浏览器内核加载进度，并在上方显示进度条

扫码借书界面
user-permisson获取照相机权限
io.github.xudaojie.qrcodelib实现二维码扫描

借阅记录界面
ListView+adapter+asynhttpClient实现借阅记录录入

扫码结果界面
OnActivityResult实现监听扫码返回结果
 背景采用高斯模糊
使用ViewPager将界面分为上下两个部分，
ActivityOptionsCompat.makeSceneTransitionAnimation实现切换动画效果

活动信息界面
listView+adapter+cardView实现活动信息展示

预约记录查看界面
listView+adapter+cardView
asynhttpClient实现加载被预约书籍内容
