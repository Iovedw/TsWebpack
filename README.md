## 项目说明
    Typescript：[@typescript](https://www.tslang.cn/docs/home.html)
    webpack：[@webpack](https://www.webpackjs.com/concepts/)
    
## 知识点
    ```
    0. npm init -y # 使用npm默认package.json配置
        0-1. npm init # 或者使用交互式自行配置，遇到选项如果直接敲回车即使用括号内的值
        0-2. src：用来存放项目的开发资源，在 src 下创建如下文件夹：
            0-2-1: utils：和业务相关的可复用方法
            0-2-2: tools：和业务无关的纯工具函数
            0-2-3: assets：图片字体等静态资源
            0-2-4: api：可复用的接口请求方法
            0-2-5: config：配置文件
            0-2-6: typings：模块声明文件
            0-2-7: build：webpack 构建配置
    1.npm install -g typescript 
    2.tsc -v
    3.npm install typescript #然后我们还需要在项目里安装一下typescript，因为我们要搭配使用webpack进行编译和本地开发，不是使用tsc指令，所以要在项目安装一下：
    4.npm install tslint -g # 配置tslint 1. 首先需要在全局安装TSLint，记着要用管理员身份运行：
        4-1.tslint -i #然后在我们的项目根目录下，使用TSLint初始化我们的配置文件：
        4-2.项目根目录下多了一个TSLint的配置文件
            4-2-1. defaultSeverity #是提醒级别，如果为error则会报错，如果为warning则会警告，如果设为off则关闭，那TSLint就关闭了；
            4-2-2. extend   #可指定继承指定的预设配置规则
            4-2-3. jsRules  #用来配置对和文件的校验，配置规则的方法和下面的rules一样
           *4-2-4. rules    #我们要让TSLint根据怎样的规则来检查代码，都是在这个里面配置，比如当我们不允许代码中使用 
            4-2-5. rulesDirectory #可以指定规则配置文件，这里指定相对路径
    5. 配置webpack
        5-1. npm install webpack webpack-cli webpack-dev-server -D
        5-2. npm install cross-env #安装插件，来获取当前是开发还是生产环境
        5-3. 编写src/build/webpack.config.js
            #配置详情请看文件webpack.config.js
        5-4.#这里我们用到了两个webpack插件，第一个clean-webpack-plugin 插件用于删除某个文件夹，
        我们编译项目的时候需要重新清掉上次打包生成的dist文件夹，然后进行重新编译，所以需要用到这个插件将上次打包的dist文件夹清掉。
        第二个html-webpack-plugin插件用于指定编译的模板，这里我们指定模板为"./src/template/index.html"文件，打包时会根据此html文件生成页面入口文件

    6. npm run start # 启动本地服务
        #若报错 (compilation.mainTemplate.applyPluginsWaterfall is not a function)
            解决方法：1.npm uninstall html-webpack-plugin   2.npm install html-webpack-plugin  
    6-1. npm run build # 项目打包
        # 若报错 (ERROR in Entry module not found: Error: Can't resolve 'ts-loader' in '/Users/dw/Typescript/test')
            解决方法：npm install ts-loader --save
    7.tsc --init
        3-1. 配置tsconfig 将js / ts 拆分两个文件夹
        3-2. 终端 -> 运行生成任务（实时更改）
    8. ts引js框架
        4-1. npm install --save-dev @types/jquery
        4-2. npm install jquery
    ```