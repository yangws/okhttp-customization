# OkHttp 定制版本

为了防止多份 OkHttp 库在同一个 Android 工程中发生冲突, 需要一份和官方库包名不同的版本，存放在此仓库中。 

## 官方版本源码下载

[下载 OkHttp 3.12.8](https://codeload.github.com/square/okhttp/zip/parent-3.12.8)

下载依赖库:
- [OkIO 1.15.0](https://codeload.github.com/square/okio/zip/okio-parent-1.15.0)

[编译工具 IntelliJ IDEA 下载页面](https://www.jetbrains.com/idea/)

## 本仓库代码编译步骤
1. 使用 IDEA 打开 okio 工程目录，在 maven 任务里点击 package，生成 customio-x.x.x.jar
2. 使用 IDEA 打开 okhttp 工程目录
3. 修改 okhttp module 的 pom 文件，并把修改包名编译后的 customio-x.x.x.jar 放入项目里，进行本地引用, 具体见修改后的 pom 文件
4. 最后点 maven 任务里的 package 打包成 customhttp3-x.x.x.jar

## 官方代码到本仓库代码改包名步骤

在 IDEA 工程中使用批量搜索替换:
1. OkIO 工程中替换 okio module 包名为（customio）
2. 把 import okio 换成 import customio, 进行 build 检查是否有包引用错误
3. 按上面说明的"编译步骤"编译，检查有无错误，并排除错误
