# 欢迎使用yamecent-admin后台管理

## 环境要求

| 依赖 | 说明 |
| -------- | -------- |
| [PHP](https://secure.php.net/manual/zh/install.php) | `PHP7+` |

------
## 项目简介
yamecent-admin是一款基于laravel框架进行封装的后台管理系统,其中包含：

* rbac权限管理模块
* 完整的ui组件(外部引入)
* 图片上传,网络请求等常用的js公共函数
* 持续维护中...


------
## 安装教程
* 执行安装命令 `composer create-project woann/yamecent-admin` 或者`git clone git@github.com:woann/yamecent-admin.git` 
* 配置域名(按laravel项目正常配置即可,解析到public目录)
* 如发现权限相关问题 执行 chown -R 用户名:用户组 项目目录
* 访问域名,登录即可进入管理系统
* 首次访问域名时会跳转至安装页面![1541490225.jpg](https://upload-images.jianshu.io/upload_images/14769055-a5c3bae19726a891.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 填写完数据表配置之后，点击安装即可（有点小慢，喝口水）
* 安装完之后就可以使用刚刚提交的管理员账号密码登录了（如果您想重新安装，要将/app/install/install.lock 文件删掉，重新访问网址即可）
* UI参考地址: http://demo.cssmoban.com/cssthemes5/twts_141_PurpleAdmin/pages/ui-features/buttons.html


## js函数列表

| 函数 | 用途 |
| -------- | -------- |
| myRequest(url,type,data,success,error){} | 发起ajax请求(包含laravel的token验证,loading等) |
| function myConfirm(msg,confirm){} | 发起询问框 |
| checkForm(){} | 验证表单 |
| cutStr(){} | 限制td字数 |
## 富文本
 * html
 ```html
    <div class="form-group " id="text" style="display: none;">
        <label >富文本</label>
        <textarea  placeholder="请在此处编辑内容"  id="editor" style="height:400px;max-height:400px;overflow: hidden"></textarea >   
    </div>
 ```
 * javascript
 ```javascript
    var editor = new wangEditor('editor');
    editor.config.uploadImgUrl = "/admin/wangeditor/upload";
    // 隐藏掉插入网络图片功能。该配置，只有在你正确配置了图片上传功能之后才可用。
    editor.config.hideLinkImg = false;
    editor.create();
 ```
 * 示例
![富文本编辑器](http://upload-images.jianshu.io/upload_images/14769055-b42c1b3b4f4ab979.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 列表批量操作
* html
 ```html
    <!--按钮-->
    <button type="button" class="btn btn-sm btn-gradient-danger btn-icon-text" onclick="batch('/admin/user/del/')">
       <i class="mdi mdi-delete btn-icon-prepend"></i>批量删除
    </button>
```
```html
    <!--全选复选框-->
    <tr>
        <th width="3%">
            <div class="form-check">
                <label class="form-check-label">
                    <input type="checkbox" class="form-check-input batch-all">
                </label>
            </div>
         </th>
        ...
    </tr>
```
```html
    <!--列表复选框-->
    <tr>
        <td>
            <div class="form-check">
               <label class="form-check-label">
                   <input type="checkbox" class="form-check-input td-check" value="{{ $v->id }}">
               </label>
            </div>
        </td>
        ...
    </tr>
 ```

 * 示例
![批量操作](http://upload-images.jianshu.io/upload_images/14769055-62ba575064933680.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

[1]: https://www.woann.cn
[2]: http://xjj.woann.cn
[3]: http://demo.woann.cn

部分截图:

![admin](http://upload-images.jianshu.io/upload_images/14769055-6cdf8ab92efbd3a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![admin](http://upload-images.jianshu.io/upload_images/14769055-2653d63deeb067ff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![admin](http://upload-images.jianshu.io/upload_images/14769055-d06caa6cbe6d27bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![admin](http://upload-images.jianshu.io/upload_images/14769055-b5451e2355517c2b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

作者 [@woann][1]  [@xjj][2]   
2018 年 10月 30日    
