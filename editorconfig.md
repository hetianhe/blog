## 概念
每个开发者都有自己的代码风格，例如：
* 用`tab`缩进而不用`space`
* 每个`tab`缩进4列
* 使用新行作为文件的结束

当多个开发者共同维护同一个项目时，保持代码风格统一是非常重要的，  
EditorConfig是一个用于维护一致的代码风格的跨编辑器/IDE的插件。

## 使用
* 在项目根目录下创建.editorconfig文件 `touch .editorconfig`  
* 安装EditorConfig插件([具体见官网](https://editorconfig.org/#download))
* [属性说明-官方wiki](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties)

## 注意

* 文件查询  
插件会从文件所在目录开始并逐级向上寻找.editorconfig。  
只有在某个配置文件的root为true或已经到达根目录时，才会停止。

* 层叠配置优先级  
被打开文件相对路径越短的配置文件的优先级越高。  
当多个配置文件冲突时，优先级高的会覆盖优先级低的。  
举例：  
当打开learn_editorconfig/src/index.js时，learn_editorconfig/src/.editorconfig的优先级比learn_editorconfig/.editorconfig要高。

## 示例
vue官方示例
```.editorconfig
# https://editorconfig.org

root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true

[*.md]
insert_final_newline = false
trim_trailing_whitespace = false
```

## 思考
* 场景：每次新建一个项目，都要手创建.editorconfig文件，copy相同内容，或者搜索资料  
* 思考：遵循`程序员的行事准则` `编程基本原则`[DYR Don't repeat yourself](https://zh.wikipedia.org/wiki/%E4%B8%80%E6%AC%A1%E4%B8%94%E4%BB%85%E4%B8%80%E6%AC%A1)，为了减少重复的动作，提高工作效率，是否可以开发一个选项式的工具来快速生成配置文件  
* 方案：开发一个npm插件/脚手架，通过选项方式来生成(快速生成 or 自定义)
```
npx create-editor-config
npm init editor-config
```
