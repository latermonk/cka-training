# DAY01

## cka考试概况

费用$300含补考

在线远程监考 3小时实际操作
开卷可以查看 kubernetes.io的内容
有效期2年
网络连通性 熟练度



消息通信 list-watch  

pod的实际体现：
是通过 workload ,service,label and selector来体现的
 
## workload:

Deployment

StatefulSet

DaemonSet

Job

Deployment 是一组Pod的抽象。所以删除deployment的时候要去删除Deployment

而不是删除Pod,否则有可能无法删除

## Service:

pod 对外的组合

给一组pod设置反向代理

## label & selector
label:标志着一个pod, 就是一个pod的属性

给对象打标记，类似于数据库中的条件查询

方便selector使用

selector:调度和编排的依据

##  k8s API基本构成
API对象的基本构成：

*   typeMeta

*   objectMeta
*   spec
*   status

记住API的方法：

弄清楚各种workload的类型和特点，然后去记忆

熟练使用：

kubectl explain pod.x.x.x

来查询具体的属性和含义

例如：

kubectl explain pod.spec.volumes.storageos

逐级往下查

故障定位：

kubectl describe

kubectl apply 可以检测之前的 对象定义是否存在，有更新的话才会产生新的对象

技巧：

kubectl describe 查看资源缩写

namespace相关的操作

创建

在内部进行操作

删除

-----

yaml文件的生成：

*   kubectl run --image=nginx my-deployment -o yaml --dry-run > mydeploy.yaml

*   kubectl get statefulset/foo -o=yaml --export > new.yaml

*   kubectl explain pod.spec.affinity.podAffinity

--

查看创建过程的命令

kubectl get po --watch

# 作业：

## 1.通过命令行，使用nginx镜像创建一个pod。Pod的名称为<hwcka-001-你的华为云id>

将所用命令、创建的Pod完整yaml截图上传

kubectl run hwcka-001-sprout-wang --image nginx --port 9999

## 2.通过单个命令创建一个deployment并暴露Service[只用一个命令]

–deployment和Service名称为<hwcka-002-你的华为云id>

–使用nginx镜像，deployment拥有2个pod

–将所用命令、创建的deployment和service完整yaml截图上传
todo