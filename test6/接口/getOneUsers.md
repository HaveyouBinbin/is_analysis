<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getOneUsers  [返回](../README.md)
[添加用户](../用例/添加用户.md)，[查看用户](../用例/查看用户.md)，[修改用户](../用例/修改用户.md)，[删除用户](../用例/删除用户.md)

- 功能：
    用于获取用户信息，用户包括教务管理员、教师和学生。
    
- 权限：
    - 系统管理员：返回系统管理员选择查询的用户（教务管理员、教师或者学生）的信息，即接口参数sysAdmin_id必须等于登录教师的sysAdmin_id
    
- API请求地址： 
    接口基本地址/v1/api/getOneUsers/<sysAdmin_id>

- 请求方式 ：
    GET

- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |sysAdmin_id|系统管理员编号|
    
- 返回实例：

    如果系统管理员查询的用户是学生：

        {
            "status": true,
            "info": null,
            "total": 30,
            "data": [
                {
                "ID":"201510414109",
                "name":"郭钊彬",
                "class_dept":"软件工程1班"
                "github_username":"haveyoubinbin",
                "type":"学生"
                }, 
                {
                ...其他学生
                }
            ] 
        }

    如果系统管理员查询的用户是教师：

        {
            "status": true,
            "info": null,
            "total": 15,
            "data": [
                {
                "ID":"20156666",
                "name":"赵卫东",
                "department":"信工学院同创工作室"
                "github_username":"haveyoubinbin",
                "type":"教师"
                },
                {
                ...其他教师
                }
            ]
        }

    如果系统管理员查询的用户是教务管理员：

        {
            "status": true,
            "info": null,
            "total": 5,
            "data": [
                {
                "ID":"6666",
                "name":"鹿晗",
                "department":"教务处"
                "github_username":"haveyoubinbin",
                "type":"教务管理员"
                },
                {
                ...其他教务管理员
                }
            ]
        }

- 返回参数说明：

    如果系统管理员查询的用户是学生：

   |参数名称|说明|
   |:---------:|:--------------------------------------------------------|
   |status|bool类型，true表示正确的返回，false表示有错误|
   |info|返回结果说明信息|
   |ID|学生学号|
   |name|用户的真实姓名|
   |class_dept|班级|
   |github_username|gitHub用户名|
   |type|用户类型：学生|

    如果系统管理员查询的用户是教师或教务管理员：

   |参数名称|说明|
   |:---------:|:--------------------------------------------------------|
   |status|bool类型，true表示正确的返回，false表示有错误|
   |info|返回结果说明信息|
   |ID|教师工号/教务管理员编号|
   |name|用户的真实姓名|
   |department|部门名称|
   |github_username|gitHub用户名|
   |type|用户类型：教师/教务管理员|

