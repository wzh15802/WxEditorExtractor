# 微信编辑器收费模板提取助手V2.3

### 已支持平台：

| 平台名称     | 素材 | 模板 | 其他     | 注意事项                                                     |
| ------------ | ---- | ---- | -------- | ------------------------------------------------------------ |
| 135编辑器    | 支持 | 支持 | 无       | 素材模板一个框内                                             |
| 96编辑器     | 支持 | 支持 | 无       | 素材、模板需区分填写                                         |
| 365编辑器    | 支持 | 支持 | 无       | 素材、模板需区分填写，支持英文ID+数字ID                      |
| 小墨鹰编辑器 | 支持 | 支持 | 无       | 素材、模板需区分填写；<br />素材**必须**要粘到135编辑器使用，<br />模板**必须**要粘到小墨鹰编辑器使用 |
| 主编编辑器   | 支持 | 支持 | 无       | 素材、模板需区分填写                                         |
| 壹伴编辑器   | 支持 | 支持 | 无       | 素材、模板需区分填写                                         |
| 易点编辑器   | 支持 | 支持 | 无       | 素材、模板需区分填写                                         |
| 秀米编辑器   | 无   | 无   | 风格排版 | 仅支持风格排版，**必须**粘贴到135编辑器使用                  |

### 免责声明

**本工具适用于快速提取微信编辑器模板(代码)，仅供学习交流，勿用于其他用途。**

**本工具完全免费，如从其他渠道购买所得，请举报+差评！**

工具支持各平台的样式+模板提取，复制的模板内容（不限于版式、图片等）可能存在风险。仅供学习交流使用，如用于其他用途，一切风险责任请使用者自行承担……

【帮助手册】：[点击查看](https://docs.qq.com/doc/DZHVpektYYkZhdnBr)

【更新日志】：[点击查看](https://mp.weixin.qq.com/s/zDzj4-tJRiCsKpehL4loVA)

【下载地址】：[点击下载](https://github.com/wzh15802/WxEditor/releases/tag/%E5%BE%AE%E4%BF%A1%E7%BC%96%E8%BE%91%E5%99%A8)



### 更新日志
2.3 

优化 程序异步处理，防止假死

修复 易点元素提取

2.2

新增 软件版本检测，有新版本会提示(非强制更新)

优化 秀米风格排版提取方式

优化 秀米提取逻辑，提升兼容性

修复 小墨鹰部分<div>布局模板在135粘贴后编辑错行的问题

修复 秀米风格排版提取后图片高度拉伸变形及头部区域文字不能编辑的问题


2.1

新增 支持秀米风格排版提取

修复 小墨鹰样式/模板提取

暂停 易点平台样式提取

2.0

新增 支持所有平台统一在一个工具使用

新增 365平台对模板提取的支持

优化 部分渠道提取方案

1.0

每个平台一个提取软件

### 开发背景

本质很简单，懂得前端知识自然懂得如何操作，但对于没有基础的人来说，这个不用去找，可以直接一键自动复制

本人没有专业的开发知识，这个只是PyQt5的学习作品，故可能会存在有一些未知兼容问题，欢迎反馈！



### 常见问题

**【1】支持获取什么？**

支持各大编辑器的样式和模板的提取

**【2】如何知道ID？**

**有三个地方可以获取：**

第一种，在各编辑器平台一般左侧会存在样式或模板列表中，鼠标悬停即有提示ID;

第二种，在编辑器平台的样式或模板中心，列表页或某个样式的详情页都会有ID（部分平台是预览时就会显示ID）

第三种，从样式中心点击进入的模板详情，浏览器窗口中的链接，最后的一串数字即为ID

**【3】SVG的怎么提取？**

本工具不支持SVG提取，提取SVG模板是分分钟的事，但是提取出来是源码，而各大SVG编辑器中无法导入外部源码(仅支持插入他们自己的组件)，故即使提取出模板源码但如果不懂前端知识也无法使用。

如果懂前端知识的也就不需要用本工具提取源码了。

**【4】提取源码成功后怎么办？**

1. 随意找一个编辑器平台(除特殊标注外-均已做提取成功的提示，一般情况不需要遵循135提取的必须135用，粘到96等等其他平台也能用，素材/模板在各个平台之间都是互通的。)

2. 在编辑器工具栏找到[html]或源码图标工具，点击进入

3. 粘贴提取的源码

4. 重新点击[html]或源码图标工具，退出源码模式

5. 自由发挥

**【5】点击按钮出现无响应假死状态？**

因部分解析方法限制，极少数情况下会有卡顿情况，可等待10-30秒完成提取。超过60秒就重启工具吧。



### 其他方案

##### 1. 万能前端大法

浏览器审查元素(一般为F12)，找到类似于
\<section>\</section>
直接复制使用，此方法技术要求相对较高(需要懂前端知识)

![]()![](https://raw.githubusercontent.com/hiboxs/a/main/image.png)

##### 2. 油猴(篡改猴插件)

以下内容基于篡改猴，先[安装篡改猴浏览器插件](https://www.tampermonkey.net/index.php?browser=firefox&locale=zh)，再点击`添加新脚本` ，将以下内容复制到新脚本保存，保持启用状态即可

此方法仅支持编辑器页面左侧快速插件，无法获取模板、及素材库页面的内容

````js
// ==UserScript==
// @name         微信编辑器爆破
// @namespace    https://greasyfork.org/users/734068
// @homepage	 https://gitee.com/yeminch/hack-wxeditor
// @version      1.17
// @description  [请勿商用]无视微信编辑器VIP限制，可以使用VIP排版（135/365/96/zhubian/xmyeditor/wxeditor/yibanbianji/yiban.io）
// @author       Yim @ yeminch@qq.com
// @match        *://*.135editor.com/*
// @match        *://www.135editor.com/js/ueditor/dialogs/135editor/imgstyle.html*
// @match        *://bj.96weixin.com/*
// @match        *://www.wxeditor.com/*
// @match        *://www.zhubian.com/*
// @match        *://yibanbianji.com
// @match        *://yibanbianji.com/*
// @match        *://www.365editor.com/*
// @match        https://mp.weixin.qq.com/cgi-bin/appmsg*
// @match        *://*.yibanbianji.com/*
// @match        *://www.xmyeditor.com/*
// @run-at 		 document-end
// @grant    	 unsafeWindow
// @require		 https://cdn.jsdelivr.net/npm/jquery@1.11.3/dist/jquery.min.js
// @downloadURL https://update.greasyfork.org/scripts/421126/%E5%BE%AE%E4%BF%A1%E7%BC%96%E8%BE%91%E5%99%A8%E7%88%86%E7%A0%B4.user.js
// @updateURL https://update.greasyfork.org/scripts/421126/%E5%BE%AE%E4%BF%A1%E7%BC%96%E8%BE%91%E5%99%A8%E7%88%86%E7%A0%B4.meta.js
// ==/UserScript==

(function() {
    'use strict';
    // Your code here...
	let setting={
		item:null,
        type:1,
	};
    var lists=[];
	function init(){
		var host = window.location.host;
		if(host.search(/www.135editor.com/)>=0) init135();
        if(host.search(/bj.96weixin.com/)>=0) init96();
        if(host.search(/www.wxeditor.com/)>=0) initYD();
        if(host.search(/www.zhubian.com/)>=0) initZB();
		if(host.search(/yibanbianji.com/)>=0) initYB();
        if(host.search(/weixin.qq.com/)>=0) initWXYB();
        if(host.search(/www.xmyeditor.com/)>=0) initXMY2();
        if(host.search(/www.365editor.com/)>=0) init365();
	}
	function addStyle(cssText) {
		let a = document.createElement('style');
		a.textContent = cssText;
		let doc = document.head || document.documentElement;
		doc.appendChild(a);
	}
	function init135(){
		 $('<div class="ym_wx_plus_btn">强势插入</div>').appendTo('body').on('click',function(){
			if(!setting.item) return false;
			var h;
			var ue = unsafeWindow.top.UE.getEditor('WxMsgContent');
            if(setting.type==1){
				h = setting.item.find('._135editor').html();
			}else if(setting.type==2){
				h = setting.item.html();
				unsafeWindow.window.top.$("#preview_modal_").hide();
			}
			if(h) ue.setContent(h, true);
		});
        $("body").on('mousemove',function(event){
			var mouseX = event.pageX,mouseY = event.pageY;
            var ele,x1,x2,y1,y2;
            if($(event.target).attr("id")=="template-modal"){
                ele = $(event.target);
                y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
                setting.type=2;
                setting.item=$(".l-img .Content-body");
                $('.ym_wx_plus_btn').css('left','auto').css('right','20px').css('top',(y1+50)+'px').show();
            }else{
                ele = $(event.target).parents('li.style-item');
                if(ele.length<=0) ele = $(event.target).parents('li.vip-style');
                if(ele.length>0){
                    y1 = ele.offset().top;
                    y2 = y1 + ele.height();
                    x1 = ele.offset().left;
                    x2 = x1 + ele.width();
                    if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                        unsafeWindow.window.top.$('.ym_wx_plus_btn').hide();
                        setting.item=null;
                    }else{
                        unsafeWindow.window.top.$('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+5)+'px').show();
                        setting.type=1;
                        setting.item=ele;
                    }
                }else{
                    if(!$(event.target).hasClass('ym_wx_plus_btn'))unsafeWindow.window.top.$('.ym_wx_plus_btn').hide();
                }
            }
		});
	}
    function init96(){
        setInterval(function(){
            $('.rich_media_content').attr('data-vip',1);
        },2000);
    }
    function initYD(){
        setInterval(function(){
            $('.yead_editor').attr('data-use',1);
        },2000);
    }
    function initZB(){
        setInterval(function(){
            unsafeWindow.AlreadyLogin = true;
            unsafeWindow.localStorage.year=99;
            if($('#user_vip').length==0){
                $('body').append('<div style="display:none"><div id="user_vip" data-vip="4"></div></div>');
            }else{
                $('#user_vip').attr('data-vip',4);
            }
            $('.rich_media_content').attr('data-vip',1);
        },2000);
    }
	function initYB(){
        $('<div class="ym_wx_plus_btn">强势插入</div>').appendTo('body').on('click',function(){
			if(!setting.item) return false;
            var ue = UE.getEditor('ueditor-container');
			var h;
			if(setting.type==2){
				h=setting.item.children().eq(0).prop('outerHTML');
			}else if(setting.type==3){
				h=setting.item.find('.template-set').html();
				setting.item.find('.close-icon').trigger('click');
			}else{
				h=setting.item.find('.html-container').html();
			}
			if(h) ue.setContent(h, true);
		});
        $("body").on('mousemove',function(event){
            var mouseX = event.pageX,mouseY = event.pageY;
			var ele,x1,x2,y1,y2;
			if($(event.target).parents('.material-item').length>0){
				ele = $(event.target).parents('.material-item');
                y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
                if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+5)+'px').show();
                    setting.item=ele;
					setting.type=1;
                }
			}else if($(event.target).parents('.img-list-ul').length>0){
				ele = $(event.target).parents('li');
				setting.type=2;
                y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
                if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+2)+'px').show();
                    setting.item=ele;
                }
			}else if($(event.target).parents('.part-style-template').length>0){
				ele = $(event.target).parents('.style-template-item');
				setting.type=1;
                y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
                if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+2)+'px').show();
                    setting.item=ele;
                }
            }else if($(event.target).parents('.template-set-preview').length>0){
				ele = $(event.target).parents('.template-set-preview');
				setting.type=3;
                y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
                if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x1+10)+'px').css('top',(y1+5)+'px').show();
                    setting.item=ele;
                }
			}else{
                if(!$(event.target).hasClass('ym_wx_plus_btn'))$('.ym_wx_plus_btn').hide();
            }
		});
    }
    function initWXYB(){
        var wxybinit=false;
        $('<div class="ym_wx_plus_btn">强势插入</div>').appendTo('body').on('click',function(){
			if(!setting.item) return false;
			var h;
			if(setting.type==2){
				h=setting.item.children().eq(1).prop('outerHTML');
			}else if(setting.type==3){
				h=setting.item.find('.dynamic-material-html-container').html();
			}else if(setting.type==4){
				h=setting.item.find('.template-set').html();
				setting.item.find('.close-icon').trigger('click');
			}else if(setting.type==5){
				//长图需要跨域通信 懒得弄
				//var ue = unsafeWindow.top.UE.getEditor('WxMsgContent');
				//h=setting.item.find('.editor-canvas').html();
				//unsafeWindow.window.top.$('.gaoding-editor-iframe-dialog').prev('div').remove();
				//unsafeWindow.window.top.$('.gaoding-editor-iframe-dialog').remove();
			}else{
				h=setting.item.find('.html-container').not('.mpa-hide').html();
			}
			if(h){
                unsafeWindow.window.__MP_Editor_JSAPI__.invoke({
                    apiName: 'mp_editor_insert_html',
                    apiParam: {
                        html: h,
                        isSelect: false
                    },
                    sucCb: (res) => {console.log('设置成功', res)},
                    errCb: (err) => {console.log('设置失败', err)}
                })
            }
		});

        $("body").on('mousemove',function(event){
            var mouseX = event.pageX,mouseY = event.pageY;
			var ele,x1,x2,y1,y2;
			ele = $(event.target).parents('.material-item');
			if($(event.target).parents('.img-list-ul').length>0){
				ele = $(event.target).parents('li');
				y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+2)+'px').show();
                    setting.item=ele;
					setting.type=2;
                }
			}else if($(event.target).parents('.material-item.material-item-svg').length>0){
				y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-150)+'px').css('top',(y1+25)+'px').show();
                    setting.item=ele;
					setting.type=3;
                }
			}else if($(event.target).parents('.material-item.style-template-item').length>0){
				if(! ele.hasClass('part-template-item')){
					$('.ym_wx_plus_btn').hide();
					setting.item=null;
					return;
				}
				y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+5)+'px').show();
                    setting.item=ele;
					setting.type=1;
                }
			}else if($(event.target).parents('.material-item').length>0){
				y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1+5)+'px').show();
                    setting.item=ele;
					setting.type=1;
                }
			}else if($(event.target).parents('.template-set-preview').length>0){
				ele = $(event.target).parents('.template-set-preview');
				y1 = ele.offset().top;
				y2 = y1 + ele.height();
				x1 = ele.offset().left;
				x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
					$('.ym_wx_plus_btn').hide();
					setting.item=null;
				}else{
					$('.ym_wx_plus_btn').css('left',(x2-180)+'px').css('top',(y1+25)+'px').show();
					setting.item=ele;
					setting.type=4;
				}
			}else if($(event.target).parents('.design-editor').length>0){
				$('.ym_wx_plus_btn').hide();
				return;
				ele = $(event.target).parents('.design-editor');
				y1 = ele.offset().top;
				y2 = y1 + ele.height();
				x1 = ele.offset().left;
				x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
					$('.ym_wx_plus_btn').hide();
					setting.item=null;
				}else{
					$('.ym_wx_plus_btn').css('left',(x2-180)+'px').css('top',(y1+25)+'px').show();
					setting.item=ele;
					setting.type=5;
				}
			}else{
				if(!$(event.target).hasClass('ym_wx_plus_btn'))$('.ym_wx_plus_btn').hide();
			}
		});
    }
    function initXMY2(){
		 $('<div class="ym_wx_plus_btn">强势插入</div>').appendTo('body').on('click',function(){
			if(!setting.item) return false;
            var h=setting.item.find('.LB-sl-content').html().replace(/class="xmyedltor"/g,'class="xmyeditor"').replace(/data-xmy="xmyeditor.com"/g, '');//.replace(/<div/g,'<section').replace(/<\/div>/,'</section>');
			if(h) ue.setContent(h, true);
		});
        $("body").on('mousemove',function(event){
			var mouseX = event.pageX,mouseY = event.pageY;
            var ele = $(event.target).parents('li.LB-sl-li');
			if(ele.length>0){
                var y1 = ele.offset().top;
                var y2 = y1 + ele.height();
                var x1 = ele.offset().left;
                var x2 = x1 + ele.width();
                if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1)+'px').show();
                    setting.item=ele;
                }
            }else{
                if(!$(event.target).hasClass('ym_wx_plus_btn'))$('.ym_wx_plus_btn').hide();
            }
		});
	}
    function init365(){
		 $('<div class="ym_wx_plus_btn">强势插入</div>').appendTo('body').on('click',function(){
			if(!setting.item) return false;
            var h;
			if(setting.type==1) h=setting.item.find('.KolEditor').html();
			else if(setting.type==2){
				h= setting.item.children().eq(2).prop('outerHTML');
				$('.phone-perview-inner .close-btn').trigger('click');
			}
			if(h) UE.instants["ueditorInstant0"].setContent(h,true);
			$('.ym_wx_plus_btn').hide();
		});

        $("body").on('mousemove',function(event){
			var mouseX = event.pageX,mouseY = event.pageY;
			var ele,x1,x2,y1,y2;
            ele = $(event.target).parents('.content-material .material-list');
			if(ele.length>0){
				setting.type=1;
				y1 = ele.offset().top;
                y2 = y1 + ele.height();
                x1 = ele.offset().left;
                x2 = x1 + ele.width();
				if( mouseX < x1 || mouseX > x2 || mouseY < y1 || mouseY > y2){
                    $('.ym_wx_plus_btn').hide();
                    setting.item=null;
                }else{
                    $('.ym_wx_plus_btn').css('left',(x2-90)+'px').css('top',(y1)+'px').show();
                    setting.item=ele;
                }
			}else{
				ele = $(event.target).parents('.phone-perview-inner .preview-body');
				if(ele.length>0){
					y1 = ele.offset().top;
					y2 = y1 + ele.height();
					x1 = ele.offset().left;
					x2 = x1 + ele.width();
					setting.type=2;
					setting.item=ele;
					$('.ym_wx_plus_btn').css('left',(x2-150)+'px').css('top',(y1+5)+'px').show();
				}else{
					if(!$(event.target).hasClass('ym_wx_plus_btn'))$('.ym_wx_plus_btn').hide();
				}
			}
		});
	}
	addStyle(`
	.ym_wx_plus_btn{position:absolute;display:none;left:0;top:5px;cursor:pointer;width:90px;height:30px;line-height:30px;background:#f00;color:#fff;text-align:center;z-index:99999999;}
	`);
	init();
})();
````
