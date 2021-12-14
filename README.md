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


![image](https://user-images.githubusercontent.com/63569149/146040969-3172b4ea-a8f7-4fd7-b15f-086e7d4d412b.png)
