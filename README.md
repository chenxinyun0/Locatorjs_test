### 作用： 可以通过点击UI页面跳转到代码编辑器指定行数   
<br>
    
首先需要安装扩展https://chrome.google.com/webstore/detail/locatorjs/npbfdllefekhdplbkdigpncggmojpefi

### react框架项目引入：
```
npm install -D @locator/runtime
npm install -D @locator/babel-jsx
```

### babel配置文件增加
```
 plugins: [
      ["@locator/babel-jsx/dist", {
        env: "development"
      }]
    ],
```

### 入口文件增加
```
import setupLocatorUI from "@locator/runtime";
if (process.env.NODE_ENV === "development") {
  setupLocatorUI();
}
```

### 官网支持很多框架
[官方地址](https://www.locatorjs.com/)

缺点：
* 多开工作台时，可能会出现工作台跳转错误的情况，但是有规律可寻，只是需要开发时注意下即可，很好避免。 
* 目前不支持vue2版本，可以在老项目内使用vue-dev-tools 扩展进行代码跳转，此插件本身是支持的，可以选中组件树的某个节点，点击右下角的图标进行跳转，但是缺点是只能跳转到指定组件文件中，但是无法精确到指定行数。

优点：  
大大缩短了寻找代码位置的时间，尤其是繁重的老代码、项目内结构混乱的代码和重业务逻辑的项目。