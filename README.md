# bower 命令

### 搜索包
会列出搜索相关的包

    bower serarch bootstrap

### bower info  查看包信息

    bower info bootstrap
    # 查看具体版本的信息
    bower info bootstrap#3.0.0


### bower install 按照包
会安装包得依赖

    bower install bootstrap
    # 安装指定版本
    bower install bootstrap#3.0.0

### bower.json
类似node的package.json,有了bower.json，使用bower install 会下载里面指定的依赖文件

    # 交互生成bower.json
    bower init
    [?] name: bower_learn
    [?] version: 0.0.1
    [?] description: Learn bower
    [?] main file:
    [?] what types of modules does this package expose?
    [?] keywords:
    [?] authors: youqingkui <youqingkui@qq.com>
    [?] license: MIT
    [?] homepage:
    [?] set currently installed components as dependencies? Yes
    [?] add commonly ignored files to ignore list? Yes
    [?] would you like to mark this package as private which prevents it from being accidentally published to the registry? No

    {
      name: 'bower_learn',
      version: '0.0.1',
      authors: [
        'youqingkui <youqingkui@qq.com>'
      ],
      description: 'Learn bower',
      license: 'MIT',
      ignore: [
        '**/.*',
        'node_modules',
        'bower_components',
        'test',
        'tests'
      ],
      dependencies: {
        bootstrap: '~3.3.1'
      }
    }

    [?] Looks good? Yes


### 更新包
在安装的当前目录使用`bower list` 可以列出目录下面安装的包，已经版本，如果要更新，修改bower.json 里面的依赖版本，然后使用`bower update` 即可更新包


### 将后面安装的包存在bower.json依赖
如果后面安装包，并且想存在依赖总，后面可以跟`--save` 或`-s`

    bower install somepackage --save


### 卸载安装的包
卸载使用`bower uninstall backbone` 即可从本地卸载包，如果同时需要清楚依赖后面可以

    bower uninstall backbone --save

### 清除不需要的依赖包
如果安装某个了包，但是bower.json中的依赖没有存在此包，可以使用prune清除bower.json依赖里面不存在的包。

    bower prune


### 使用缓存离线安装包
如果使用install 安装了某个包，那bower会把它缓存起来

    bower cache list   # 列出所有缓存的包
    bower install backbone --offline --save # 使用缓存安装backbone
    bower cache clean # 清空所有缓存


### 更新版本信息
版本信息有3个部分，如0.0.0，可以使用`version`来修改版本信息

    bower version 0.0.2
    bower version patch # 最后面的0进一位
    bower version minor # 中间部分的0进一位
    bower version major # 最前面的0进一位

### 修改版本号，并提交git信息
使用bower的提交信息，类似于git的`commit ` 修改版本号，并且将信息提交到git

    bower version patch -m "%s 修改版本号" # %s 为提交的版本占位符



