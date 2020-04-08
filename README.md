
# ui-team 
![Who owns BFF](document/WhoOwnsBFF.png)
- 前端团队拥有并负责开发BFF，可以采用同一样的技术栈如小程序前端采用H5、javascript，BFF采用nodejs
- 前端团队专注用户界面与用户体验而无需等待业务逻辑实现团队提供的api
- 这样减少与业务逻辑实现团队沟通，在还没有业务逻辑api之前，前端团队自己可以在BFF完全MOCK数据来支持用户界面或用户体验的开发

# bi-team  
![Who owns BFF](document/WhoOwnsBFF2.png)
![Who owns BFF](document/WhoOwnsBFF1.png)
- owns api, 
- microservices 
- repositories


[Ok Google, how to add git submodule external library gradle android](https://medium.com/@alteromusica/git-submodule-gradle-shared-library-d40383403b59)

1. 添加git submodule
```shell script
git submodule add https://github.com/covid19angels/doper-graphql-gateway.git

git submodule add https://github.com/covid19angels/kgis-datalake-dgraph.git
```

2. 修改settings.gradle
```shell script

pluginManagement {
    repositories {
        mavenLocal()
        gradlePluginPortal()
    }
}

rootProject.name = 'bi-team'

include ':doper-graphql-gateway'
project(':doper-graphql-gateway').projectDir = new File(settingsDir, './doper-graphql-gateway')

include ':kgis-datalake-dgraph'
project(':kgis-datalake-dgraph').projectDir = new File(settingsDir, './kgis-datalake-dgraph')



```

