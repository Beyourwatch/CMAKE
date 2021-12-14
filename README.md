# CMAKE

#定义cmake版本
cmake_minimum_required(VERSION 3.10)

#定义项目
project (hellocmake LANGUAGES CXX)

#把文件作为库 SHARED 动态库 需要so文件一起，运行时候调用   STATIC 静态库 编译到可执行文件里，文件大
add_library(hellolib SHARED hello.cpp)

*add_library(test STATIC source1.cpp source2.cpp) 生成libtest.a 静态库

*add_library(test SHARED source1.cpp source2.cpp) 生成libtest.0 动态库


#可执行文件 hello， 只需要 main.cpp
add_executable(hello main.cpp)

#链接 hellolib
target_link_libraries(hello PUBLIC hellolib)



![image](https://user-images.githubusercontent.com/63569149/146033380-48bbe439-b777-41d3-ba0f-22a07ffb4a99.png)


# 附带子目录后，add_subdirectory 会找不到头文件
需要增加 target_include_directories(hello PUBLIC $PATH) 附加目录

PUBLIC 会传递到 上级文件 CMAKELISTS  PRIVATE 不会，仅在下级的CMAKELISTS 使用

![image](https://user-images.githubusercontent.com/63569149/146042136-7e98715a-a927-49c1-be79-826a906425ad.png)



# 导入第三方库
#1. 头文件
![image](https://user-images.githubusercontent.com/63569149/146043875-48141a68-70e8-4a34-ba35-e3d6c33cf108.png)

![image](https://user-images.githubusercontent.com/63569149/146044042-403c78b1-07ce-4065-87c2-1083f3b652e9.png)

#2作为子模块
![image](https://user-images.githubusercontent.com/63569149/146044321-1478a76c-ee4d-42f1-927a-7f0d2b3d472f.png)













