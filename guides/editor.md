## 编辑器

推荐使用 Visual Studio Code(以下简称 vscode). 下文提到的 IDE 或者编辑器如果没有其他说明均指 vscode.

### vscode 的配置

1. vscode 的项目级别配置，也就是团队成员共享的配置，使用 Workspace Settings 配置。对应 `.vscode/settings.json` 配置文件。
2. 项目推荐安装的插件配置在 `.vscode/extensions.json` 配置文件。有需要跟团队成员共享，或者要求安装的插件，将插件 ID 添加进 `.vscode/extensions.json` 文件中。

### 缩进与换行

1. 安装插件 `"EditorConfig.editorconfig"`
2. 如果没有的话，在项目根目录创建 `.editorconfig` 配置文件。

推荐使用如下配置。

```ini
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
```

### 代码格式化

1. 安装 Prettier 插件 `esbenp.prettier-vscode`
2. Vue 项目安装 `octref.vetur` 插件。
3. TypeScript 项目推荐安装插件 `eg2.tslint`, vscode 本身已经对 TypeScript 提供了很多支持。可以查看相关配置项，然后按需要配置到项目配置文件中。
4. 项目配置应该配置成保存时格式化。

推荐如下配置：

```json
{
  "tslint.autoFixOnSave": true,
  "files.autoSave": "onFocusChange",
  "[typescript]": {
    "editor.codeActionsOnSave": {
      "source.organizeImports": true
    }
  },
  "editor.rulers": [80, 120],
  "editor.formatOnType": false,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "typescript.format.enable": true,
  "typescript.validate.enable": true,
  "typescript.suggestionActions.enabled": true
}
```
