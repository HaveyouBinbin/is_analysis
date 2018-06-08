<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getOneTests  [返回](../README.md)
[添加实验](../用例/添加实验.md)，[查看实验](../用例/查看实验.md)，[修改实验](../用例/修改实验.md)，[删除实验](../用例/删除实验.md)

- 功能：
    用于获取课程的实验信息。
    
- 权限：
    - 教师：只能返回教师自己选择的课程的实验，即接口参数teacher_id必须等于登录教师的teacher_id
    
- API请求地址： 
    接口基本地址/v1/api/getOneTests/<teacher_id>

- 请求方式 ：
    GET

- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |teacher_id|教师工号|
    
- 返回实例：

        {         
            "status": true,
            "info": null,
            "courses_id": "201510414158",
            "courses_name": "信息系统分析与设计",
            "total": 6,
            "data": [
                {
                "test": "实验1",
                "test_id": "201511",
                "name": "业务流程图建模",
                "weight": "30%",
                "date": "2018-06-20 12:02:39",
                "delete_date": "2018-06-01 12:02:39",
                "amend_date": "2018-06-01 20:02:39",
                }, 
                {
                ...其他实验
                }
            ] 
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |courses_id|课程代码|
  |courses_name|课程名称|
  |total|实验个数|
  |data|实验信息|
  |test|实验几|
  |test_id|实验编号，如果为空，则表示没有实验|
  |name|实验名称|
  |weight|实验权重，每项实验的权重按百分比计算|
  |date|提交实验截止时间，如果为空，则表示未发布实验|
  |delete_date|添加实验的时间|
  |amend_date|修改实验的时间|

