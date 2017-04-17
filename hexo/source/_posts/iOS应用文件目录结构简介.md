title: iOS应用文件目录结构简介
date: 2015-12-26 15:24:51
tags:
---
### iOS 标准目录结构
出于安全考虑，iOS只有特定目录可以写入数据。 当一款应用安装在设备上后，系统会创建一些系统目录给应用使用，一款应用只有权限访问其自己的路径下的数据。


## AppName.app
整个应用的bundle文件。此目录包含整个应用和其所使用到的所有资源。 *此路径不能写， 只可读*， 如果强行写入，会改变安装时在系统注册的该目录的签名，如果签名改变，系统会组织程序启动。

## Documents/
用于存储用户产生的内容。 此目录会被iTunes*默认备份*

## Documents/Inbox
此目录用于保存用于其他应用打开的文件。 例如，Mail应用汇将和此应用有关的附件保存于这个路径。 Documents interaction Controllers 也会放文件于此目录。

自己应用可以读取和删除此目录文件，但是*不能创建新文件或者写入已经存在的文件*， 如果要对该目录文件进行修改，请将要修改的文件移除到其他目录。
*此目录默认被iTunes备份*

## Library/
此目录用于保存非用户数据文件。 Library下的子目录可以用于保存那些不希望用户看到的数据文件。*不要用Library下的目录保存用户数据文件*

Library目录下(除了Caches目录及其子目录)会被*iTunes默认备份*

## tmp/
用于那些不需要在每次启动需要持久化的临时文件。手动删除那些此路径下不用的临时文件。当应用没有运行时，系统也许会删除此目录下的文件。

*此目录默认不会被iTunes备份*


### 应用产生的文件应该放在哪
为了避免iOS设备间同步和备份流程耗时太久，应该对文件归属目录的选择特别注意。

* 将用户数据保存于 Documents/. 用户数据包括那些需要让暴露给用户的文件 --- 用户可以创建，删除，编辑的文件。 例如，对于视频和音频应用，用户数据包括用户下载过的文件等。
* 将应用创建的文件保存于Library/Application support/路径下。此目录下，用于保存应用自身使用，不暴露给用户的数据文件。包括数据文件，配置文件，模板文件和版本特定的资源文件等。
* 谨记保存于Documents/ 和 Application support/ 目录下的文件是*默认备份的*。可以使用```[NSURL setResourceValue:forKey:error:]```使用```NSURLIsExcludeFromBackupKey``` key. *任何可以被重新下载的文件，一定不要进行备份*。
* 将数据缓存数据保存于Library/Caches 目录下。 缓存数据是那些没用该数据，应用也可以正常运行的数据， 但如果有缓存数据，会提高应用的性能。 例如，数据库缓存文件，可以下载的内容等。 *注意：系统也许会删除Caches/下的文件，来释放磁盘空间*

参考: [File System programming guide](https://developer.apple.com/library/ios/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html)
