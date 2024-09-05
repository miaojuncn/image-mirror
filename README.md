# image-mirror

`image-mirror`是一个帮助加速下载某些难以下载的镜像的工具, 可以加速下载各国外大厂的某些无法下载的镜像

## Features
- 支持公网所有基于 Docker Registry V2 搭建的 docker 镜像仓库同步
- 除了 gcr.io, k8s.gcr.io, registry.k8s.io, quay.io, ghcr.io 仓库可以加速外, 公网的公开仓库大概都可以
- ...

## 使用

### fork 使用(推荐)
- 阿里云目前提供个人版镜像仓库, 限额`3`个`namespace`, `300`个镜像

1. fork 本仓库, 然后在仓库设置中打开`issue`功能
2. 设置自己的目标仓库信息

#### 需要设置一些变量`variables`
- **TARGET_NAMESPACE**: 目标`NAMESPACE`, 该例子中应该设置为`mj-mirror`
- **TARGET_REGISTRY**: 目标仓库, 该例子中应该设置为`registry.cn-hangzhou.aliyuncs.com`
- **TARGET_REGISTRY_USER**: 目标仓库的用户名
 
#### 一些`secrets`
- **TARGET_REGISTRY_PASSWORD**: 目标仓库的密码

该例子中, 需要确保使用目标仓库的用户名和密码, 使用命令`docker login registry.cn-hangzhou.aliyuncs.com`能够成功登录  
3. 按照直接使用的方式在自己的仓库提交 issue

### 直接使用
提交一个 issue 即可, issue 内容为你无法正常下载的镜像，[示例](https://github.com/miaojuncn/image-mirror/issues/1)如下: 
![image](https://github.com/user-attachments/assets/b3de9437-dc6e-482d-bd81-e6edaa27d6e7)

就会触发 GitHub action, 同步镜像到`registry.cn-hangzhou.aliyuncs.com`(默认同步到`mj-mirror`的`NAMESPACE`下)

GitHub action bot 会在 action 完成后, 提示同步成功的镜像, 并且定期关闭 issue


## Tools
- [image-syncer](https://github.com/AliyunContainerService/image-syncer) 是一个镜像同步工具, 可用来进行多对多的镜像仓库同步, 支持目前绝大多数主流的镜像仓库服务  



