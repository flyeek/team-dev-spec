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
