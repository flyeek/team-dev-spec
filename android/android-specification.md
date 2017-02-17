# Android Development Specification Manual

## IDE
Android Studio(stable channel)

## Code Style
We Applying the famous [Google-Java-Style](https://google.github.io/styleguide/javaguide.html) as our team code standard.

In order to using this along with IDE, just importing the [IDE preference file](https://github.com/qiandaodao/team-dev-spec/raw/master/android/assets/qiandaodao-code-style-settings-for-as.jar). Remember to **reformat code(including optimize-imports)** as soon as finishing editing source file.

## Git Branch Manage Practice
We apply simplified `git-flow` as our code branch manage practice. The overview is as the followings:

![git-flow](https://github.com/qiandaodao/team-dev-spec/raw/master/android/assets/qiandaodao-git-flow.png)

There are three types of branch:
- Master branch. Correspond to the online version of production. Branch name is **master**.
- Develop branch. Correspond to the developing process of versions. Branch name is **master**.
- Feature branch. Correspond to the specific feature which is not from product department, for example the refactor of some functions. Branch name is **feature/xxxx** and use dash-case as naming rule, for example *feature/optimize-download-module-performance*.

The tag must be made at the same time of releasing a version.

## Lint
Lint is the process to check source files for potential bugs and optimization improvements for correctness, security, performance, usability.

The involving source files including the following types:
- Java and XML files
- Icons
- ProGuard Configuration files

We integrate this checking process with the IDE by import [lint file](https://github.com/qiandaodao/team-dev-spec/raw/master/android/assets/qiandaodao-lint-for-as.xml) into `Preference -> Editor -> Inspection -> Profile`.

The lint process take effect in the following two stages:
- Pop-up hint within editor page.
- Scan and Lint at the very first period of compiling and packaging process.

We employ the above lint to our daily development and test, as well as being a part of our CI/CD System.

You can manually trigger the `lint` by running `Analyze -> Inspect Code`, and get the result on `Inspection Panel`.

## Resource Name Rules
### 颜色
分为基础颜色、通用颜色和特殊颜色三种类型，其中前两者定义于res/values/colors.xml内。
- 基础颜色，是为了方便其它地方直接引用而定义的一系列颜色。命名规范为`color_<description[_<auxiliary>]>[_alpha_<value>]`，例如`<color name="color_purple">#9c27b0</color>`、`<color name="color_indigo_700">#303f9f</color>`、`<color name="color_black_alpha_50">#80000000</color>`。注意，名称和十六进制颜色值中的**字母为小写**。

- 通用颜色，是对应设计规范的一系列颜色值，包括品牌色、背景色、文字颜色等。命名规范为`pallete_<type>_<description_and_more>`，例如`<color name="pallete_brand_primary">#00cc99</color>`，`<color name="pallete_background_actionbar">#00cc99</color>`。

- 特殊颜色，是指特定页面元素所使用的颜色，直接写在相应的布局或代码中。

### 尺寸
分为通用尺寸、模块尺寸和特殊尺寸三种类型，前两者定义于res/values/dimens.xml内。
- 通用尺寸，是对应设计规范的一系列尺寸值，包括页面边距，按钮，分隔符，元素间隔等。命名规范为`common_[type]_<description_and_more>`。例如，`<dimen name="common_screen_side_margin">15dp</dimen>`。

- 模块尺寸，是某个功能模块对应的相关页面中使用到的尺寸值。命名规则为`<module>_[type]_<description_and_more>`，写在dimens.xml中，作为单独的代码块并加上起始备注。

- 特殊尺寸，是指特定页面中使用的尺寸值，一般仅在单页面内使用。直接写在相应的布局或代码中。

### 字符串
分为通用字符串和模块字符串三中类型，前者定义于res/values/strings.xml中，后者定义于res/values/strings_<module>.xml中。
- 通用字符串，包括应用名称，常用按钮文本，toast文本等。命名规范为`common_<description_and_more>`。

- 模块字符串，是各个功能模块内使用到的文本。命名规范为`<module>_<description_and_more>`，当包括格式化文本时，命名规范为`<module>_format_<description_and_more>`。模块内不同页面使用到的文本，需要作为独立代码块，并添加起始备注。

### 可绘制资源（drawable）
在实际使用中，drawable主要包括bitmap、shape drawable、state list、level list。
- bitmap，分为图标、通用背景图、模块背景图三种类型。图标命名规范为`icon_<description_and_more>.xxx`。通用背景图命名规范为`common_bitmap_[type]_<description_and_more>.xxx`。特殊背景图命名规范为`<module>_bitmap_[type]_<description_and_more>.xxx`。

- shape drawable，分为图标、通用背景图、模块背景图三种类型。在使用上优先级高于bitmap。图标命名规范为`icon_<description_and_more>`。通用背景图命名规范为`common_shape_[type]_<description_and_more>.xml`。特殊背景图命名规范为`<module>_shape_[type]_<description_and_more>.xml`。

- state list，分为通用selector和模块selector两种类型。通用selector命名规范为`common_selector_[type]_<description_and_more>.xml`。模块selector命名规范为`<module>_selector_[type]_<description_and_more>_selector.xml`。

- level list，分为通用level list和模块level list两种类型。通用level list命名规范为`common_level_list_[type]_<description_and_more>.xml`。模块level list命名规范为`<module>_level_list_[type]_<description_and_more>.xml`。

### 动画
分为通用动画和模块动画两种类型。
- 通用动画，包括页面切换动画，对话框动画等。命名规则为`common_anim_<description_and_more>.xml`。

- 模块动画，是模块内某个(或某些)页面元素使用到的动画。命名规范为`<module>_anim_<description_and_more>.xml`。

### 样式
样式是设计规范在代码中最直接的体现形式。分为通用样式和模块样式两类。
- 通用样式，包括各种button、text等。命名规范为`Common[Type]<description_and_more>`。

- 模块样式，是模块内用到的各种View组件的样式定义。命名规范为`<Module>[Type]<description_and_more>`。

### 布局
布局有如下两个维度。
- 业务逻辑类型。包括通用模块（base activity、dialog、自定义view等）和根据业务划分的不同模块，在命名中分别用`common`和`<module>`来表示。

- 加载位置。可以分为activity、fragment、adapter、dialog等。在命名中使用各自名字来表示。

基于以上两个维度，布局的命名规范为`<common | <module>>_<position>_<description_and_more>.xml`
