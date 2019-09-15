
V免签  —— 个人开发者收款解决方案
===============



V免签(PHP) 是基于Thinkphp5.1 + mysql 实现的一套免签支付程序，主要包含以下特色：

 + 收款即时到账，无需进入第三方账户，收款更安全
 + 提供示例代码简单接入
 + 超简单Api使用，提供统一Api实现收款回调
 + 免费、开源，无后门风险
 + 支持监听店员收款信息，可使用支付宝微信小号/模拟器挂机，方便IOS用户
 + 免root，免xp框架，不修改支付宝/微信客户端，防封更安全
 
> 如果您不熟悉PHP环境的配置，您可以使用Java版本的服务端（ https://github.com/szvone/Vmq ）

> 监控端的开源地址位于： https://github.com/szvone/VmqApk

> V免签的运行环境为PHP版本>=5.6。

> V免签仅供个人开发者调试测试使用，请勿用于非法用途，商用请您申请官方商户接口

> v免签开发交流群：992029073 （群已被封，作者QQ：7876632【问功能怎样的别加我，不回答，免费开源系统，自行搭建测试，不提供技术支持】）

> bug反馈请建立issues


## 前言


V免签为完全开源项目，开源项目意味着作者没有任何收入来源，仅凭个人空闲时间开发，如果您有经济条件，您可以赞助本项目的开发（下方收款码），如果您不想赞助，也请您点击上面的Star给一个星星，也是对我莫大的认同，感谢各位的支持。

![微信赞助](wx.jpg)![支付宝赞助](zfb.jpg)

## 原理
+ 用户扫码付款 -> 收到款项后手机通知栏会有提醒 -> V免签监控端监听到提醒，推送至服务端->服务端根据金额判断是哪笔订单

## 安装
 + 推荐使用宝塔面板安装，以下教程为宝塔面板安装教程，其他环境请参考自行配置

    1、下载源代码,Clone or download->Download ZIP
    
    2、宝塔面板中新建网站，设置：
        
        + 网站目录->运行目录 设置为public并保存
        + 伪静态 设置为thinkphp并保存
        + 默认文档 设置将index.html放在第一行并保存
    
    3、打开网站目录 config/database.php ，设置好您的mysql账号密码。
    
    4、导入数据库文件（位于根目录）vmq.sql到您的数据库。
    
    5、至此网站搭建完毕，请访问后自行修改配置信息！默认后台账号和密码均为admin


 > 升级说明：请您直接下载新版本覆盖旧版本即可！
 
 
## 调用

 + 请部署完成后访问后台，有详细的Api说明
 
 
## 注意

  + 本系统原理为监控收款后手机的通知栏推送消息，所以请保持微信/支付宝/V免签监控端后台正常运行，且添加到内存清理白名单！

  + v免签面向用户是个人开发者，如果您不懂如何开发网站，那么v免签不适合您的使用！
  
  + v免签的原理是监控手机收到收款后的通知栏推送信息，所以不适合于商用多用户的情况，如果您想用于商用，请二次开发！
  
  + v免签是免费开源产品，所有程序均开放源代码，所以不会有收费计划，因此作者不可能教会每个人部署安装，请参考文档多百度谷歌，v免签使用具有一定的技术门槛，请见谅！
  
  + v免签的监控端并不适配所有手机，遇到手机无法正常使用的时候，请您更换手机或使用模拟器挂机！
  
  + v免签拥有双语言服务端，当您使用php版本服务端遇到问题的时候，请您尝试使用java版本服务端，php版本服务端配置略复杂，需要配置伪静态规则，请知悉！

  + 正常的安装步骤简略如下
    + 下载服务端部署(GitHub中下载的为最新版)
    + 登录网站后台更改系统设置
    + 打开网站后台监控端设置
    + 下载监控端
    + 安装监控端后使用手动配置或扫码配置
    + 监控端中点击开启服务跳转到辅助功能中开启服务
    + 开启服务后返回v免签点击检测监听权限
    + 如果显示监听权限正常，至此安装完毕，如果只收到通知栏推送的测试通知，则系统不兼容无法正常监听
    + 如果显示监听权限正常，还是无法正常运行，那么请确定微信是否关注 “微信支付” 和 “微信收款助手” 这两个公众号
  
  + 手机设置步骤（教程为MIUI系统，非MIUI系统请参考教程进行设置）
    + 关闭系统神隐模式
       
        （旧版MIUI系统）在系统【设置】 - 【其他高级设置】 - 【电量与性能】 - 【神隐模式】 - 【V免签监控端】设置为关闭
        
        （新版MIUI系统）在系统【设置】 - 【其他高级设置】 - 【电量与性能】 - 【省电优化】 - 【应用智能省电】，将V免签监控端、微信、支付宝的3个APP全都改为无限制
    
    + 添加内存清理白名单
    
    + 关闭WIFI优化
    
        （旧版MIUI系统）在系统【设置】 - 【WLAN】 -【高级设置】 -【WLAN优化】，关闭它。
    
        （新版MIUI系统）在系统【设置】 - 【WLAN】 -【高级设置】 - 【在休眠状态下保持WLAN网络连接】改为“始终”
   
    + 开启推送通知
    
        系统【设置】 - 【通知和状态栏】 - 【通知管理】中，找到这3个App，把里面的开关全部打开
        
    + 在微信的【设置】 - 【勿扰模式】中，关闭勿扰模式
    
    + 在微信的公众号，关注 【微信收款助手】 这个公众号
    
    + 在支付宝的主页，上方搜索框 搜索 【支付助手】 ，进入支付助手，右上角小齿轮，打开【接收付款消息提醒】


    
  + v免签支持的通知有：
    + 支付宝个人收款的推送通知
    + 支付宝商家二维码的收款推送通知
    + 支付宝店员通绑定的店员账号收款的推送通知
    + 微信二维码收款推送通知
    + 微信店员收款推送通知
           
## 更新记录
 + v1.9.1（2019.09.15）
    + 二维码识别出错增加解决方法：在其他网站（草料二维码识别）识别二维码内容后，将内容重新生成成二维码图片上传。
    
 + v1.9（2019.09.11）
    + 修复一些已知的BUG
    + 因为很多人的服务器时间不准确，因此删除时间校验，不会出现客户端时间错误了
    + 增加主页服务器基本配置的显示列表
    
 + v1.8.1（2019.05.22）
    + 增加详细的手机端设置教程
    + 同步最新版监控端App
    
 + v1.8（2019.05.16）
    + 更新监控端APP到1.6版本，理论支持更多手机
    + 尝试修复偶然情况下锁定金额无法被释放的问题
    
 + v1.7.2（2019.05.12）
    + 修复当通知地址带有GET参数的时候，无法正常通知的问题
    
 + v1.7.1（2019.05.07）
    + 修复上个版本更新后订单金额异常的问题

 + v1.7（2019.05.06）
    + 修复部分情况下无法自动释放被锁定金额的情况（本版本数据库有变动，旧版升级请覆盖文件后，将tmp_price表中增加一列，字段名为oid，类型varchar(255),如果您不会增加，请删除原有数据库并重新导入vmq.sql）

 + v1.6.2（2019.04.30）
    + 修复部分情况下出现订单已过期，但是页面还在倒计时的问题

 + v1.6.1（2019.04.26）
    + 再次优化二维码识别，使用js解析二维码，如果失败，则使用PHP解析
    
 + v1.6（2019.04.25）
    + 优化二维码识别，使用js解析二维码，解决部分二维码识别返回false问题 
    
 + v1.5（2019.04.24）
    + 同步最新版APP
    + 添加注意事项说明，完善README.md文档

 + v1.4.1（2019.04.22）
    + 修复删除未支付状态的订单时不自动释放锁定金额的问题
    + 修复创建订单时返回的二维码与支付方式不符合的问题

 + v1.4（2019.04.21）
    + 修复订单过期不自动释放锁定金额的问题
    + 修复订单超出负荷问题
      
 + v1.3（2019.04.20）
    + 删除数据库文件中的默认系统设置，防止误导用户
    + 更新监控App到v1.3版本，趋于稳定，可以正常使用
      
 + v1.2（2019.04.19）
    + 整理代码，重新优化APP兼容性
    + 添加店员到账支持，添加后可以实现安卓备用机/模拟器 挂小号取收款通知，方便IOS用户，
       + 微信绑定店员方式=>微信->收付款->二维码收款->收款小账本->添加店员接收通知
       + 支付宝绑定店员方式=>我的->商家服务->店员通->立即添加
    + 服务端修复一堆BUG，建议更新到此版本
   
 + v1.1.1（2019.04.19） 
   + 修复后台点击补单，补单成功订单未设置成成功状态
   + 修复后台首页金额统计保留两位小数
   + 修复修改系统设置引发的监控端状态重置问题
   + 新增创建订单API接口增加notifyUrl和returnUrl参数，可以在创建订单的时候设置回调接口
   
 + v1.1（2019.04.18） 
   + 打包thinkphp框架上传
   
 + v1.0（2019.04.18） 
   + PHP初版发布

## 版本预告

+ 待v免签测试稳定后，将会着手开发对接v免签的发卡平台，也是开源免费，敬请期待！

## 版权信息

V免签遵循 MIT License 开源协议发布，并提供免费使用，请勿用于非法用途。


版权所有Copyright © 2019 by vone (http://szvone.cn)

All rights reserved。

