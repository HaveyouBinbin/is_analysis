<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：setOneReleaseCourses  [返回](../README.md)
[发布课程](../用例/发布课程.md)

- 功能：
    用于系统自动设置一门课程的发布学期、发布者工号、姓名和发布时间。
    
- 权限：
    - 教务管理员：可以返回所有课程
    
- API请求地址：
    接口基本地址/v1/api/setOneReleaseCourses

- 请求方式 ：
    POST
    
- 请求实例：

        {
            "courses_id": "978-7-302-32982-502",
            "name": "Python与机器学习实践",
            "desc": "与时俱进，现在人工智能学习非常火，学生应该掌握这方面的知识",
            "eduAdmin_id": "20038888",
            "eduAdmin_name": "陈赫",
            "release_term": "2017-2018",
            "release_date": "2018-06-01 23:02:39",
        }

- 请求参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |courses_id|本次课程代码|
  |name|本次课程的名称|
  |desc|本次课程简介|
  |eduAdmin_id|发布本次课程的教务管理员的工号，如果为空，则表示课程未发布|
  |eduAdmin_name|发布本次课程的教务管理员的姓名，如果为空，则表示课程未发布|
  |release_term|发布本次课程的学期|
  |release_date|本次课程发布的时间|

- 返回实例：

        {
            "status": true,
            "info": null
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
