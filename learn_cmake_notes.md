# 学习 CMake 的笔记

## 特殊命令的要点
1. include_directories([AFTER|BEFORE] [SYSTEM] dir1 [dir2 ...]) 添加头文件搜索路径
	1. AFTER：表示在系统搜索路径之后【默认是在系统搜索路径之后】
	2. BEFORE：表示在系统搜索路径之前
	3. 该命令会对系统所有的目标起作用
2. link_directories([AFTER|BEFORE] directory1 [directory2 ...]) 添加库文件搜索路径
	1. 该命令只会对定义在该命令之后的目标起作用
3. add_test(<name> <command> [<arg>...])
	1. 添加一个测试目标 name ，执行命令 command arg 列表是 command 的参数
4. enable_testing()
	1. 这个命令要放到源码的根目录，因为 ctest 希望去 build 根目录查找 test 文件
5. find_library (<VAR> name1 [path1 path2 ...])
	1. 查找单个库文件时不需要添加 NAMES 指定库名字
