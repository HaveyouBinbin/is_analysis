<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getOneScoreItems  [返回](../README.md)
[添加评分项](../用例/添加评分项.md)，[查看评分项](../用例/查看评分项.md)，[修改评分项](../用例/修改评分项.md)，[删除评分项](../用例/删除评分项.md)

- 功能：
    用于获取课程的实验的评分项信息。
    
- 权限：
    - 教师：只能返回教师自己选择的课程的实验的评分项，即接口参数teacher_id必须等于登录教师的teacher_id
    
- API请求地址： 
    接口基本地址/v1/api/getOneScoreItems/<teacher_id>

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
            "test": "实验1",
            "test_id": "201511",
            "test_name": "业务流程图建模",
            "total": 5,
            "data": [
                {
                "scoreItem_id": "11",
                "name": "文档整体",
                "standard": "文档内容详实、规范，美观大方",
                "fullMarks": "20",
                "valuate": "完美",
                "delete_date": "2018-06-01 20:02:39",
                "amend_date": "2018-06-01 20:02:39",
                }, 
                {
                ...其他评分项
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
  |test|实验几|
  |test_id|实验编号，如果为空，则表示没有实验|
  |test_name|实验名称|
  |total|评分项个数|
  |data|评分项信息|
  |scoreItem_id|评分项编号，如果为空，则表示没有评分项|
  |name|评分项名称|
  |standard|评分标准|
  |fullMarks|分数|
  |valuate|评价|
  |delete_date|添加评分项的时间|
  |amend_date|修改评分项的时间|

