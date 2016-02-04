#创建工程
![](https://confluence.jetbrains.com/download/attachments/53330077/sbt_new_project.png?version=1&modificationDate=1392310107000&api=v2)
<br>
#添加插件assembly
## 插件作用
### 打fat jar
## 添加方法
### 打开project/plugins.sbt添加以下内容
addSbtPlugin("com.eed3si9n" % "sbt-assembly" % "0.14.1")
<br>
#添加依赖
### 打开工程根目录下的build.sbt文件添加以下内容
//指定mainClass
mainClass in (Compile, packageBin) := Some("com.kunyandata.newsparser.OperateHbase.HbaseOperation")
//jar包名
name := "newspaper"
//工程版本
version := "1.0"
//scala版本
scalaVersion := "2.10.5"
//添加依赖
libraryDependencies += "org.scala-lang" % "scala-compiler" % "2.10.5"
//解决依赖重复的问题
assemblyMergeStrategy in assembly := {
  case PathList("javax", "servlet", xs @ _*) => MergeStrategy.last
  case PathList("javax", "activation", xs @ _*) => MergeStrategy.last
  case PathList("javax", "el", xs @ _*) => MergeStrategy.last
  case PathList("org", "apache", xs @ _*) => MergeStrategy.last
  case PathList("com", "google", xs @ _*) => MergeStrategy.last
  case PathList("com", "esotericsoftware", xs @ _*) => MergeStrategy.last
  case PathList("com", "codahale", xs @ _*) => MergeStrategy.last
  case PathList("com", "yammer", xs @ _*) => MergeStrategy.last
  case "about.html" => MergeStrategy.rename
  case "META-INF/ECLIPSEF.RSA" => MergeStrategy.last
  case "META-INF/mailcap" => MergeStrategy.last
  case "META-INF/mimetypes.default" => MergeStrategy.last
  case "plugin.properties" => MergeStrategy.last
  case "log4j.properties" => MergeStrategy.last
  case x =>
    val oldStrategy = (assemblyMergeStrategy in assembly).value
    oldStrategy(x)
}
//打包时跳过单元测试
test in assembly := {}
<br>
#打包命令
### 打开intellij的Terminal窗口
### 输入
### sbt clean compile assembly
### 命令执行后即可在target目录下找到jar包
<br>
#参考文章
###https://confluence.jetbrains.com/display/IntelliJIDEA/Getting+Started+with+SBT
