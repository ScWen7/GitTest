## 文档目录（点击快速导航）

- [基本用法与使用注意事项](#1用法)  

- [OkGo、OkRx、OkServer分别支持的功能列表](#3okgo目前支持)  

- [OkRx使用文档](https://github.com/jeasonlzy/OkGO/blob/master/README_RX.md)  

- [全局配置](#一全局配置)

- [请求回调方法及回调顺序介绍](#二普通请求)

- [请求基本网络数据、请求Bitmap对象、请求文件下载并回调下载进度](#1基本的网络请求)

- [上传String类型的文本、上传Json类型的文本](#4普通post直接上传string类型的文本)

- [表单上传、上传图片、上传文件并回调上传进度](#6上传图片或者文件)

- [https请求](#7https请求需要在初始化的时候配置以下代码)

- [所有请求功能的配置讲解](#8请求功能的所有配置讲解)

- [取消请求](#9取消请求)

- [同步请求](#10同步的请求)

- [请求参数的顺序](#11参数的顺序)

- [OkGo内置CallBack介绍](#三自定义callback使用)

- [JsonCallback自定义的详细原理与方法介绍](https://github.com/jeasonlzy/OkGO/blob/master/README_JSONCALLBACK.md)

- [OkGO强大的缓存使用介绍](#四缓存的使用)

- [cookie的使用与session的保持](#五cookie的使用与session的保持)

- [混淆配置](#六混淆)

  ​

## 1.用法

 * `okgo`使用的`okhttp`的版本是最新的 3.4.1 版本，和以前的 2.x 的版本可能会存在冲突。
 * `okrx`是基于`RxJava`和`RxAndroid`的扩展,如果不需要可以不必引入
 * `okserver`是对`okgo`的扩展，统一了下载管理和上传管理，对项目有需要做统一下载的可以考虑使用该扩展，不需要的可以直接使用`okgo`即可。
 * 对于缓存模式使用，需要与返回对象相关的所有`javaBean`必须实现`Serializable`接口，否者会报`NotSerializableException`。
 * 使用缓存时，如果不指定`cacheKey`，默认是用url带参数的全路径名为`cacheKey`。
 * 使用该网络框架时，必须要在 Application 中做初始化 `OkGo.init(this);`
 * `okgo`使用的`okhttp`的版本是最新的 3.4.1 版本，和以前的 2.x 的版本可能会存在冲突。
 * `okrx`是基于`RxJava`和`RxAndroid`的扩展,如果不需要可以不必引入
 * `okserver`是对`okgo`的扩展，统一了下载管理和上传管理，对项目有需要做统一下载的可以考虑使用该扩展，不需要的可以直接使用`okgo`即可。
 * 对于缓存模式使用，需要与返回对象相关的所有`javaBean`必须实现`Serializable`接口，否者会报`NotSerializableException`。
 * 使用缓存时，如果不指定`cacheKey`，默认是用url带参数的全路径名为`cacheKey`。
 * 使用该网络框架时，必须要在 Application 中做初始化 `OkGo.init(this);``okgo`使用的`okhttp`的版本是最新的 3.4.1 版本，和以前的 2.x 的版本可能会存在冲突。
 * `okrx`是基于`RxJava`和`RxAndroid`的扩展,如果不需要可以不必引入
 * `okserver`是对`okgo`的扩展，统一了下载管理和上传管理，对项目有需要做统一下载的可以考虑使用该扩展，不需要的可以直接使用`okgo`即可。
 * 对于缓存模式使用，需要与返回对象相关的所有`javaBean`必须实现`Serializable`接口，否者会报`NotSerializableException`。
 * 使用缓存时，如果不指定`cacheKey`，默认是用url带参数的全路径名为`cacheKey`。
 * 使用该网络框架时，必须要在 Application 中做初始化 `OkGo.init(this);``okgo`使用的`okhttp`的版本是最新的 3.4.1 版本，和以前的 2.x 的版本可能会存在冲突。
 * `okrx`是基于`RxJava`和`RxAndroid`的扩展,如果不需要可以不必引入
 * `okserver`是对`okgo`的扩展，统一了下载管理和上传管理，对项目有需要做统一下载的可以考虑使用该扩展，不需要的可以直接使用`okgo`即可。
 * 对于缓存模式使用，需要与返回对象相关的所有`javaBean`必须实现`Serializable`接口，否者会报`NotSerializableException`。
 * 使用缓存时，如果不指定`cacheKey`，默认是用url带参数的全路径名为`cacheKey`。
 * 使用该网络框架时，必须要在 Application 中做初始化 `OkGo.init(this);``okgo`使用的`okhttp`的版本是最新的 3.4.1 版本，和以前的 2.x 的版本可能会存在冲突。
 * `okrx`是基于`RxJava`和`RxAndroid`的扩展,如果不需要可以不必引入
 * `okserver`是对`okgo`的扩展，统一了下载管理和上传管理，对项目有需要做统一下载的可以考虑使用该扩展，不需要的可以直接使用`okgo`即可。
 * 对于缓存模式使用，需要与返回对象相关的所有`javaBean`必须实现`Serializable`接口，否者会报`NotSerializableException`。
 * 使用缓存时，如果不指定`cacheKey`，默认是用url带参数的全路径名为`cacheKey`。
 * 使用该网络框架时，必须要在 Application 中做初始化 `OkGo.init(this);``okgo`使用的`okhttp`的版本是最新的 3.4.1 版本，和以前的 2.x 的版本可能会存在冲突。
 * `okrx`是基于`RxJava`和`RxAndroid`的扩展,如果不需要可以不必引入
 * `okserver`是对`okgo`的扩展，统一了下载管理和上传管理，对项目有需要做统一下载的可以考虑使用该扩展，不需要的可以直接使用`okgo`即可。
 * 对于缓存模式使用，需要与返回对象相关的所有`javaBean`必须实现`Serializable`接口，否者会报`NotSerializableException`。
 * 使用缓存时，如果不指定`cacheKey`，默认是用url带参数的全路径名为`cacheKey`。
 * 使用该网络框架时，必须要在 Application 中做初始化 `OkGo.init(this);`



##  3.OkGo目前支持