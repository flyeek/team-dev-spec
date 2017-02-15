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
- Master branch. Correspond to the online version of production.
- Develop branch. Correspond to the developing process of versions.
- Feature branch. Correspond to the specific feature which is not from product department, for example the refactor of some functions.

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

We plan to employ the above lint to our daily development and test, as well as being a part of our CI/CD System.
