# iOS Development Specification Manual

## Language & IDE
We encourage the usage of `Swift` language.

IDE is Xcode(latest version).

## Code Style
We select the [Github-Swift-Style](https://github.com/github/swift-style-guide) as our team code standard.

Code style checking is made by [SwiftLint](https://github.com/realm/SwiftLint). The customized rules set is incorporated in project.

## Git Branch Manage Practice
We apply simplified `git-flow` as our code branch manage practice. The overview is as the followings:

![git-flow](https://github.com/qiandaodao/team-dev-spec/raw/master/ios/assets/qiandaodao-git-flow.png)

There are three types of branch:
- Master branch. Correspond to the online version of production. Branch name is **master**.
- Develop branch. Correspond to the developing process of versions. Branch name is **master**.
- Feature branch. Correspond to the specific feature which is not from product department, for example the refactor of some functions. Branch name is **feature/xxxx** and use dash-case as naming rule, for example *feature/optimize-download-module-performance*.

The tag must be made at the same time of releasing a version.

## Lint
To do.

## Resource Name Rules
### 颜色
分为基础颜色、通用颜色和特殊颜色三种类型，定义于**AppColorPallete**类中。
- 基础颜色，是为了方便其它地方直接引用而定义的一系列颜色。命名规范为`color<Description[Auxiliary]>[Alpha<value>]`，例如`colorPurple`、`colorIndigoAlpha700`。

- 通用颜色，是对应设计规范的一系列颜色值，包括品牌色、背景色、文字颜色等。命名规范为`pallete<Type><Description>`，例如`palleteBrandPrimary`，`palleteBackgroundActionbar`。

- 特殊颜色，是指特定页面元素所使用的颜色，直接写在相应的布局或代码中。

### 尺寸
分为通用尺寸、模块尺寸和特殊尺寸三种类型，定义于**AppDimen**类内。
- 通用尺寸，是对应设计规范的一系列尺寸值，包括页面边距，按钮，分隔符，元素间隔等。命名规范为`common[Type]<Description>`。例如，`commonScreenSideMargin`。

- 模块尺寸，是某个功能模块对应的相关页面中使用到的尺寸值。命名规则为`<module>[Type]<Description>`。

- 特殊尺寸，是指特定页面中使用的尺寸值，一般仅在单页面内使用。直接写在相应的布局或代码中。

### 字符串
分为通用字符串和模块字符串两种类型，定义于**Localizable.strings**中。
- 通用字符串，包括应用名称，常用按钮文本，toast文本等。命名规范为`common_<description>`。

- 模块字符串，是各个功能模块内使用到的文本。命名规范为`<module>_<description>`，当包括格式化文本时，命名规范为`<module>_format_<description>`。模块内不同页面使用到的文本，需要作为独立代码块，并添加起始备注。

### 图片
分为通用图片和模块图片两种类型。定义于**Image.xcassets**中。
- 通用图片，是app中普遍使用到的图片。命名规范为`common_<icon | background>_<description_and_more>`。

- 模块图片，是模块中使用到的图片。命名规范为`<module>_<icon | background>_<description_and_more>`。

### 布局（待完善）
布局分为storyboard和xib两种类型。分别定义于storyboard和layout文件夹中。

### 动画（待完善）
分为通用动画和模块动画两种类型。
- 通用动画，包括页面切换动画，对话框动画等。命名规则为`待定`。

- 模块动画，是模块内某个(或某些)页面元素使用到的动画。命名规范为`待定`。
