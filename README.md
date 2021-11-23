# pytracking（ATOM、DIMP、KYS、KeepTrace）
### 1 Linux系统下搭建
### 2 cuda11.1+torch1.8.1 可用（其他对应的版本应该也可用）</n>
### 3 预训练模型不要用ATOM，跑不通，因为ATOM年份较久远性能不是很好，作者不再维护
### 4 注意torch与cuda之间是否匹配
    https://pytorch.org/get-started/previous-versions/
### 5 代码尽量使用git clone 的方法直接克隆到文件夹中，防止有的软连接过不来
    git clone https://github.com/visionml/pytracking.git
    git clone https://github.com/vacancy/PreciseRoIPooling.git
### 报错提示1：
    RuntimeError: Error building extension '_prroi_pooling'
    原因1 cuda有问题
    原因2 torch与cuda不匹配，导致无法编译
    解决办法：重装与cuda匹配的torch，如果大家用的是同一个账户，服务器cuda不可重装，如果自己是一个单独的用户，可以重装
### 报错提示2：
    module 'torch' has no attribute 'rfft'
    原因：ATOM不维护了
    解决办法：运行dimp python run_tracker.py dimp dimp50 --dataset_name otb --sequence Dog --debug 1
