<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getUserInfo  [返回](../README.md)
用例： [查看用户信息](../用例/查看用户信息.md),[修改用户信息](../用例/修改用户信息.md)

- 功能：
    查看用户的所有信息。
    
- 权限：
    学生/老师/教务管理员/系统管理员：查看自己的信息，必须先登录，不能查看其他用户的信息。
    
- API请求地址： 
    接口基本地址/v1/api/getUserInfo/<user_id>

- 请求方式 ：
    GET
      
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |user_id|用户的ID号。对应表USERS.USER_ID的值|
  
- 返回实例：

        {         
            "status": true,
            "info": null,
            "ID":"201510414109",
            "name":"郭钊彬",
            "class_dept":"软件工程1班"
            "github_username":"haveyoubinbin",
            "type":"学生"            
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |ID|学生学号/教师工号/教务管理员工号/系统管理员编号|
  |name|用户的真实姓名|  
  |class_dept|班级或者部门名称|
  |github_username|gitHub用户名|
  |type|用户类型：学生/老师/教务管理员/系统管理员|

