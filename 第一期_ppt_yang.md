title: 浅谈前端架构
speaker: 不会飞的羊
transition: cards
files: /js/demo.js,/css/demo.css

[slide]

# 浅谈前端架构
## 前后端分离的前端架构
#### 演讲者：不会飞的羊

[slide]

# 为什么需要前后端分离？ {:&.flexbox.vleft}

- 前端开发重度依赖开发环境
- 前后端职责依旧纠缠不清
- 开发效率问题
- 对前端发挥的局限

[slide]

# 方案选择 {:&.flexbox.vleft}

[slide]

# 基于 Node 全栈开发 {:&.flexbox.vleft}

![image](https://camo.githubusercontent.com/ed895cf7561cb3ec07ef74aa2dea573b57dbe219/687474703a2f2f696d672e68622e616963646e2e636f6d2f3430303931653637316230626465653236653531366163303530633663616563383038383562386131326238372d374a676646685f6677363538)

[slide]

# 基于 Ajax 的单页面应用 {:&.flexbox.vleft}

- Backbone
- EmberJS
- AngularJS
- ...

[slide]

# 与后端通信 {:&.flexbox.vleft}

- socke
- restful
- no restful

[slide]

# 开发工具和环境 {:&.flexbox.vleft}

1. 管理工具 Bower
2. 模块管理工具 Seajs、Requirejs 或 Browserify
3. 任务管理工具 Grunt、Gulp

[slide]

# 测试 {:&.flexbox.vleft}

``` javascript
describe('Filter --> default filter', function () {
  var $filter;

  beforeEach(module('defaultApp.filter'));
  beforeEach(inject(function ($injector) {
    $filter = $injector.get('$filter');
  }));

  it('测试默认 filter', function () {
    expect($filter('default')('')).to.equals('demo');
  });
});
```

[slide]

# 上线处理 {:&.flexbox.vleft}

- 文件合并压缩
- 文件版本号
- CDN 加速

[slide]

# END or QA

