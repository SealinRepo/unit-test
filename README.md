### 为什么要单测
- [百度百科](https://baike.baidu.com/item/%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95/1917084?fr=aladdin)
- 单测的本质是要去发现代码中的问题。

### 现状
#### 效率
- 手动代码低效，特别是代码重构的时候
- 有些情况对象稍微大一些，我们就得不停的手动set，耗费大量时间
#### 质量
- 矛盾：代码写的不好，单测的代码写的也可能会不好，所以需要通过代码按时，足够充分的Assert帮助提升质量



### 目标1：自动生成代码，提升单测效率，节省programmer的时间。
- 方向1：通过约定、注解等方式约束源代码，
- 方向2：机器学习，通过学习已有的单测代码，写新的代码
### 目标2：提升单测质量。

### 用DDD的方式开发
### #领域建模
- 用例
    - 不用的单元测试工具产生的代码不同，初期考虑Junit即可。
    - 代码生成
        - 全覆盖模式，生成新的
        - 选择性生成
        
### 问题
#### 如何解决mock代码的问题
#### 如何写调用的case
- 调用参数生成
    - 基本类型 随机生成
    - 引用类型 随机生成
        - 支持代码随机过程可视化，这样可以随意修改想要的值
- 方法调用
    - 如何做多case调用，去猜测真正的调用case
    - 私有方法处理
    - 常规方法处理
#### 如何写断言
- 根据返回值类型
    - void 
        - 方法没有入参 无需断言
        - 方法有入参 验证当前对象属性的改变
    - boolean 验证返回值 
    - 其他基本类型 验证返回值 
    - 引用类型，验证非空，验证返回值属性

### 迭代步骤
#### 实现基本功能
- 通过右键，选择生成单测，然后生成新的单测代码，就的覆盖 （已完成）
- 通过右键，选择生成单测，如果已经存在，窗口提示现状，选择性覆盖哪些方法
- 批量生成功能
- 通过入参控制生成的代码风格，也可以自动检测，比如是Junit还是Jmock判断


### 想法
#### 业务驱动单元测试
业务语言转换成测试用例，测试用例转换成代码

#### 将基本的api开放，通过集成，使用者根据自己的情况编写模板


