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

## 示例
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
