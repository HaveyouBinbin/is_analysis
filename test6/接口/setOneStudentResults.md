<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：setOneStudentResults  [返回](../README.md)
用例： [评定成绩](../用例/评定成绩.md)

- 功能：
    用于设置一个学生的部分实验的评分项的得分和评价，以及实验的总成绩。
    
    输入参数scoreItem_result不为空，自动设置update_date为当前日期，表示同时设置批改日期。
    
    输入参数scoreItem_result为空，自动设置update_date为空，表示未批改。
    
- 权限：
    教师：可以评定选择该老师的所有学生的成绩和评价。
    
- API请求地址： 
    接口基本地址/v1/api/setOneStudentResults

- 请求方式 ：
    POST
 
- 请求实例：

        { 
            "student_id": "201510315209",
            "total": 6,
            "test_data": [
                {
                "scoreItem_total": 4,
                "result": 99
                "scoreItem_data":
                    {
                    "test_id":1,
                    "scoreItem_id":1,
                    "scoreItem_result": 19
                    "general_evaluation":"实验完美，少给一分是怕他骄傲",
                    },
                    {
                    ...其他评分项
                    }
                }, 
                {
                ...其他实验
                }
            ] 
        }

- 请求参数说明:       
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学号|
  |total|本次批改的所有实验的总数，小于等于全部实验的总数|
  |test_data|实验的评分项信息|
  |scoreItem_total|本次批改的所有评分项的总数，小于等于全部评分项的总数|
  |scoreItem_data|评分项的得分和评价|
  |test_id|实验编号|
  |scoreItem_id|评分项编号|
  |scoreItem_result|评分项得分，可以为空，为空表示没有批改。|
  |result|本实验成绩，系统自动计算的，可以为空，为空表示没有批改。|
  |general_evaluation|评分项的评价，可以为空|
 
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


