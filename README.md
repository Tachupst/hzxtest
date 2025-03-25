#mykvproject
项目简介：该项目基于 基于网络层框架（reactor\io_uring\NtyCo协程）开发，构建了一个可以广泛应用的 key-value数据库。该数据库采用多种高效的的数据结构（如hash\rbtree\skiplist），用户可以根据不同的应用场景，选择不同的数据结构以存储和读取数据。
项目目的：建立一个简洁、完整、把性能做到极致的数据库，并在未来不断完善业务。
1、	网络框架：该项目基于 基于网络层框架 reactor\io_uring\NtyCo协程开发。其中协程使用开源nytco，适合io密集型高并发场景，内存开销最小（栈空间），轻量级高性能，代码复杂度较高；reactor同步io异步事件，非阻塞io，延迟较低，需要回调，复杂度较高；io_uring直接操控用户态io，避免拷贝，绕过了Linux内核协议栈，零切换，延迟极低，使用hugepage，需要维护环形队列缓冲区，需要一定内存占用，低延迟超高吞吐，API接口简单。
2、	存储引擎：rbtree、btree、hash、array、skiplist。
3、	协议设计：SET COUNT GET MOV DEL EXIST等。
4、	测试用例：连接并发量测试，QPS测试10w+。
5、	优化改进方案：内存池引入、日志引入、数据持久化存储、集群数据同步。
6、	业务承接：短链接映射存储、问答文件存储、用户信息存储等。
项目结果：该kv数据库的性能较高，根据测试结果，其QPS接近于Redis数据库的水平。
