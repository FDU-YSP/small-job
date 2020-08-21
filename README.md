## job

---------------------------

### 1. 描述

某个机器的配置为：CPU 8 cores, MEM 4G, HDD 4T

这个机器上有一个 1T 的无序数据文件，格式为 (key_size, key, value_size, value)

设计一个索引结构，使得并发随机地读取每一个 key-value 的代价最小

允许对数据文件做任意预处理，但是预处理的时间计入到整个读取过程的代价


### 2. 分析

data size: 1 TB, 无序, 格式为 (key_size, key, value_size, value)

cpu cores: 8

memery: 4G

HDD: 4T

2.1 pre-handle

split data file  =>  1TB = 8 * 128GB = 8 * 1024 * 128MB
