## commitLint
  1. 格式化规范工具
    利用commitizen,帮助我们撰写规范的提交信息
    安装commitizen和cz-customizable
      npm install -g commitizen@4.2.4
      npm install -D cz-customizable@6.3.0 
    在package.json中新增
      "config": {
        "commitizen": {
          "path": "node_modules/cz-customizable"
        }
      }
    在根目录下新建.cz-config.js文件并写入配置
    之后可用git cz 代替 git commit

  2. 使用husky强制执行规范
    安装 commitlint/cli 与 commitlint/config-conventional
      npm install -D @commitlint/config-conventional@12.1.4 @commitlint/cli@12.1.4
    根目录添加commitlint.config.js配置文件
    安装husky npm install -D husky
    初始化husky npx husky install
    将husky和commitlint进行关联 npx husky add .husky/commit-msg
    在生成的 commit-msg 文件中写入指令 (替换undefined) npx --no-install commitlint --edit

https://segmentfault.com/a/1190000041878613