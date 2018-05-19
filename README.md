# day01
## 1. 项目开发准备
    项目描述
    技术选型
    API接口
    你能从此项目中学到什么?

## 2. 开启项目开发
    使用脚手架创建项目
    安装所有依赖/指定依赖
    开发环境运行
    生产环境打包与发布

## 3. 搭建项目整体界面结构
    stylus的理解和使用
        结构化, 变量, 函数/minxin(混合)
    vue-router的理解和使用
        router-view/router-link/keep-alive
        $router: 路由器对象, 包含一些操作路由的功能函数, 来实现编程式导航(跳转路由)
        $route: 当前路由对象, 一些当前路由信息数据的容器, path/meta/query/params
    项目路由拆分
    底部导航组件: FooterGuide
    导航路由组件: Msite/Search/Order/Profile

## 4. 抽取组件
    头部组件: HeaderTop, 通过slot来实现组件通信标签结构
    商家列表组件: ShopList
    
## 5. 登陆路由组件
     静态组件
     FooterGuide的显示/隐藏: 通过路由的meta
     
## 6. 后台项目
    启动后台项目: 理解前后台分离
    测试后台接口: 使用postman
    修正接口文档

## 7. 前后台交互
    ajax请求库: axios
    ajax请求函数封装: axios + promise
    接口请求函数封装: 每个后台接口


# day02
## 1. 异步数据
    封装ajax: 
        promise+axios封装ajax请求的函数
        封装每个接口对应的请求函数(能根据接口定义ajax请求函数)
        解决ajax的跨越域问题: 配置代理, 对代理的理解
    vuex编码
        创建所有相关的模块: store/index|state|mutations|actions|getters|mutation-types
        设计state: 从后台获取的数据
        实现actions: 
            定义异步action: async/await
            流程:　发ajax获取数据, commit给mutation
        实现mutations: 给状态赋值
        实现index: 创建store对象
        main.js: 配置store
    组件异步显示数据
        在mounted()通过$store.dispatch('actionName')来异步获取后台数据到state中
        mapState(['xxx'])读取state中数据到组件中
        在模板中显示xxx的数据
    模板中显示数据的来源
        data: 自身的数据(内部改变)
        props: 外部传入的数据(外部改变)
        computed: 根据data/props/别的compute/state/getters
    异步显示轮播图
        通过vuex获取foodCategorys数组(发请求, 读取)
        对数据进行整合计算(一维变为特定的二维数组)
        使用Swiper显示轮播, 如何在界面更新之后创建Swiper对象?
            1). 使用回调+$nextTick()
            2). 使用watch+$nextTick()	
    		
## 2. 登陆/注册: 界面相关效果
    a. 切换登陆方式
    b. 手机号合法检查
    c. 倒计时效果
    d. 切换显示或隐藏密码
    g. 前台验证提示
    
## 3. 前后台交互相关问题
    1). 如何查看你的应用是否发送某个ajax请求?  
        浏览器的network
    2). 发ajax请求404
        请求的路径的对
        代理是否生效(配置和重启)
        服务器应用是否运行
    3). 后台返回了数据, 但页面没有显示?
        vuex中是否有
        组件中是否读取