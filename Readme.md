#ionic系列——发送短信
###摘要：$cordovaSMS的使用介绍

##1、需求描述

    最近做的项目需要有提醒用户的功能，就是可以调用手机的发送短信功能

##2、准备

    ①、添加插件$cordovaSMS

cordova plugin add https://github.com/cordova-sms/cordova-sms-plugin.git

    ②、在controller中添加依赖

##3、代码实现

//发短信
$scope.sendMessage=function(){

    //CONFIGURATION
    
    var options = {
    
        replaceLineBreaks: false, // true to replace \n by a new line, false by default
        
        android: {
        
            intent: 'INTENT'  // send SMS with the native android SMS messaging
            
            //intent: '' // send SMS without open any other app
            
        }
        
    };
    $cordovaSms
    
        .send('18654332789', 'SMS content',options)
        
        .then(function() {
        
            // Success! SMS was sent
            
            CommonJs.AlertPopup("发送短信成功");
            
        }, function(error) {
        
            // An error occurred
            
        });
        
};
##4、注意点

    看来很多东西都需要去官网看原代码和文档，ng-cordova的文档也不全，没有介绍option怎么配置，可以从github上找一些开源的其他插件。怎么找其他的开源插件介绍一下
    
    https://github.com/cordova-sms/cordova-sms-plugin 官网地址和介绍。

##扩展知识：

    ### 1、插件扩展
    
    1）Swiper开源、免费、强大的移动端触摸滑动插件；
    
    2）LazyLoad 懒加载插件；
    
    3）zTree 树插件；给个json数据，就会形式树结构
    
      1>加C 的是核心API
      2>加E的是可扩展的
      
    4）eCharts纯javascript图表库插件
    
    5）Nicescroll滚动条插件；
    
    6）intro.js引导插件，一步一步的
      <jQuery之家>
      
    7）Pulsate.js一款脉搏特效
    
    8）Pdf.js是一个技术原型主要用于在html5平台上展示PDF文档，无需任何本地技术支持
    
    9）joint.js插件生成一个流程图（javascript交互图表工具）
    
    10）可视化D3.js，它允许绑定任意数据到DOM，然后将数据驱动转换应用到Document
    
    
    ### 2、bower 装一个插件  bower install swiper -save
    
        注意：首先bower用npm下载安装

