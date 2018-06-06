<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getEDUAdmin  [返回](../README.md)
用例： [首页显示用户列表](../用例/首页显示用户列表.md)

- 权限：
    教务管理员：可以看到WEB_SUM。
    系统管理员：可以看到WEB_SUM。

- 功能：
    返回所有教务管理员的列表。

- API请求地址：
   接口基本地址/v1/api/getEDUAdmin

- 请求方式 ：
    GET

- 请求参数说明:
    无

- 返回实例：

        {
            "status": true,
            "info": null,
            "total": 20,
            "data": [
                {"WEB_SUM": "Y,Y,Y,Y,Y,N",
                "GITHUB_USERNAME": "Chinajuedui",
                "TEACHER_ID": "20058888",
                "department": "信工学院教务处",
                "NAME": "鄢涛",
                "UPDATE_DATE": "2018-05-29 18:55:32"},
                {
                ...其他教务管理员
                }
            ]
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回学生人数|
  |data|所有学生的数组|
  |WEB_SUM|网址是否正确的汇总|
  |GITHUB_USERNAME|GITHUB 用户名|
  |TEACHER_ID|教务管理员编号|
  |department|所属部门|
  |NAME|真实姓名|
  |UPDATE_DATE|GitHUB用户名修改日期|