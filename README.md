# eslint
###### 作用
静态代码分析，问题代码协助修复集成到编码，提交，打包过程中，及早发现并协助修复问题
###### 优点
代码风格，可维护性，代码质量，发现语法错误，减小bug


### 安装

```
yarn add -D eslint
```

### 使用
一般用别人已经配置好的规则
安装Airbnb配置包：

```
yarn add -D eslint-config-airbnb-base
```

###### 获取这个包的依赖

```
npm info "eslint-config-airbnb-base@latest” peerDependencies
```

###### 安装依赖

```
yarn add -D eslint-plugin-import
```
 (支持es6的import和export)
 
添加.eslintrc.json配置文件

```js
{
  "extends": "airbnb-base”,  
  "rules": { 
    "no-console": “off” //支持console
  }
}
```
或者eslintrc.js

```js
module.exports = {
    root: true,
    extends: ['airbnb'],
    parserOptions: {
        // eslint-config-airbnb: { ecmaVersion: 6, sourceType: 'module' }
        ecmaFeatures: {
            // eslint-config-airbnb: { jsx: true, es6: true  }
            generators: true,
        },
    },
    env: {
        // eslint-config-airbnb: { node: true, es6: true }
        browser: true,
    },
    rules: {
        indent: ['error', 4],
    },
}
```
在script添加脚本命令

```js
{
  // ...
  "scripts" : {
    "test": "echo \"Error: no test specified\" && exit 1",
    "lint": "eslint **/*.js",
    "lint-html": "eslint **/*.js -f html -o ./reports/lint-results.html",
    "lint-fix": "eslint --fix **/*.js"
  },
  // ...
}
```

