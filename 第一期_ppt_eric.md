title: ember make you happy
speaker: ericzheng
transition: cards
files: /js/demo.js,/css/demo.css

[slide]

# ember make you happy
## 演讲者：Eric Zheng
## QQ:2573578564

[slide]

# How can we do if we want to develop a app ?

[slide style="background-image:url('/img/bg2.png')"]

- 设计师设计好各个尺寸的(1x,2x,3x各种小图标，界面的PSD和标记好了的设计图) {:&.moveIn}
- ios开发人员根据prd，在view中先画出来布局，然后创建手工alloc,init出来各种控件,进行定位(当然个人开发者会用什么storyboard,xib之类的,但是正规公司感觉都这样做)
- 设计好各种viewController之间的关系 {:&.moveIn}
- 与后台联调(网络数据的获取进行TableView显示,用户登陆判断和跳转等) 

[slide]
# 困难在哪里?  {:&.rollIn}
- object c语法一般人看不懂
```
  - (IBAction)animateView:(id)sender {
    CGRect cacheFrame = self.imageView.frame;
    [UIView animateWithDuration:1.5 animations:^{
        CGRect newFrame = self.imageView.frame;
        newFrame.origin.y = newFrame.origin.y + 150.0;
        self.imageView.frame = newFrame;
        self.imageView.alpha = 0.2;
    }
                     completion:^ (BOOL finished) {
                         if (finished) {
                             // Revert image view to original.
                             self.imageView.frame = cacheFrame;
                             self.imageView.alpha = 1.0;
                         }
    }];
  }
```
- 还有坑爹的android，各种组件基本名称都不一样叫法，语法也不一样，相当于重新做一个全新的{:&.moveIn}
- 开发周期实在是太长太长了{:&.moveIn}
- 每次更新都需要进行ios官方或者各大应用市场的审核{:&.moveIn}

[slide]

## 那么有没有办法?

[slide]
# hybird app ----> phonegap

[slide]

> Cordova does not provide any * UI widgets* or * MVC  frameworks *. Cordova provides only the runtime in which those can execute. If you wish to use UI widgets and/or an MVC framework, you will need to select those and include them in your application yourself as third-party material.

[slide]
# mvc framework要做什么?

- 实现业务逻辑
- 构建DOM
- 实现视图逻辑(声明式和命令式)
- 在模型和视图间进行同步
- 管理复杂的UI交互操作
- 管理状态和路由(routing)
- 创建与连接组件

[slide]
# ember为我们做了什么?

[slide]
# model

```
    App.ApplicationRoute = Ember.Route.extend({
      model: function() {
       return Ember.$.getJSON('https://api.github.com/repos/   emberjs/ember.js/pulls').then(function(data) {
      return data.splice(0, 3);
      });
    }
    });
```

[slide]
# 视图
- Handlebars+声明式语法
```
<div>
   <label>Name:</label>
   {{input type="text" value=name    placeholder="Enter your name"}}
   </div>
   <div class="text">
   <h3>My name is {{name}} and I   want to learn Ember!</h3>
   </div>
```
[slide]
# why handlebars
```
   Ember.Handlebars.registerBoundHelper('date', function(date) {
        return moment(date).format('MMM Do');
    });

```
[slide]
# Router

```
   App.Router.reopen({
    rootURL: '/blog/'
  });
```

[slide]
# How to use
```
  npm install -g ember-cli
  ember new my-app
```
[slide]
# component
```
     App.GravatarImageComponent = Ember.Component.extend({
       size: 200,
       email: '',
    gravatarUrl: function() {
    var email = this.get('email'),
        size = this.get('size');
    return 'http://www.gravatar.com/avatar/' + md5(email) + '?s=' + size;
    }.property('email', 'size')
   });
```
[slide]
# what is emberUI?
- 实现了皮肤和属性的数据的分离
[slide]
# 高性能
[slide]
- 减少HTTP请求
- 提高加载速度
- 减少浏览器运行时开销
- 减少GPU开销
- 减少内存占用
[slide]
# 可维护
- 模块化
- 自动化代码发布流程
- 监控,截屏

[slide]
# Q&A
[slide]
# The end

```
  #import <Foundation/Foundation.h>
  - (void)applicationWillTerminate:(UIApplication *)application{
    NSString *comment = @"^_^";
    NSLog(@"Thank you very much %@",comment); 
  }
```
