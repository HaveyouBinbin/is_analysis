<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getOneReleaseCourses  [返回](../README.md)
[发布课程](../用例/发布课程.md)，[选课](../用例/选课.md)

- 功能：
    返回一门已发布未被选课状态的课程的id、发布学期、发布者的工号、姓名和发布时间。
    
- 权限：
    - 教师：只能返回教师自己选择的课程，即接口参数user_id必须等于登录教师的teacher_id
    - 教务管理员：可以返回所有课程，即接口参数user_id必须等于登录教师的eduAdmin_id
    
- API请求地址： 
    接口基本地址/v1/api/getOneReleaseCourses/<user_id>

- 请求方式 ：
    GET

- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |user_id|用户的ID，教师工号或者教务管理员工号|
    
- 返回实例：

        {         
            "status": true,
            "info": null,    
            "courses_id": "978-7-302-32982-502",
            "name": "Python与机器学习实践",
            "desc": "与时俱进，现在人工智能学习非常火，学生应该掌握这方面的知识",
            "eduAdmin_id": "20038888",
            "eduAdmin_name": "陈赫",
            "release_term": "发布课程的学期",
            "release_date": "课程发布的时间",
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |courses_id|课程代码|
  |name|课程名称|
  |desc|课程简介|
  |eduAdmin_id|发布课程的教务管理员的工号，如果为空，则表示课程未发布|
  |eduAdmin_name|发布课程的教务管理员的姓名，如果为空，则表示课程未发布|
  |release_term|发布课程的学期|
  |release_date|课程发布的时间|

