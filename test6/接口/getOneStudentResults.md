<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 接口：getOneStudentResults  [返回](../README.md)
用例： [查看成绩](../用例/查看成绩.md)，[评定成绩](../用例/评定成绩.md)

- 功能：
    返回一个学生的所有实验成绩和实验评价。
    
- 权限：
    - 学生：只能查看自己的成绩、评价和评定日期，即接口参数user_id必须等于登录学生的student_id
    - 教师：可以查看选择教师自己的课程的所有学生的成绩、评价和评定日期。即接口参数user_id必须等于登录教师的teacher_id
    - 教务管理员：可以查看所有学生的成绩成绩、评价和评定日期。即接口参数user_id必须等于登录教师的eduAdmin_id
    - 系统管理员：可以查看所有学生的成绩成绩、评价和评定日期。即接口参数user_id必须等于登录教师的sysAdmin_id
    
- API请求地址： 
    接口基本地址/v1/api/getOneStudentResults/<user_id>

- 请求方式 ：
    GET

- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |user_id|用户的ID，学号，教师工号，教务管理员工号或者系统管理员编号|
    
- 返回实例：

        {         
            "status": true,
            "info": null,    
            "student_id": "201510315209",
            "github_username": "HaveyouBinbin",
            "class": "软件(本)15-1", 
            "name": "郭钊彬",
            "total": 6,
            "result": 99,
            "data": [
                {
                "test_id":1,
                "web_exists": true, 
                "scoreItem_result": 99,19,30,20,30
                "test_result": 99,
                "general_evaluation":"实验完美，少给一分是怕他骄傲",
                "update_date": "2018-05-30 15:35:40"
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
  |student_id|学号|
  |github_username|学生的gitHub用户名|
  |class|班级|
  |name|真实姓名|   
  |total|实验总数|
  |result|课程总成绩|
  |data|所有实验的成绩和评语|
  |test_id|实验编号|
  |web_exists|本实验的GitHub网页是否存在|
  |scoreItem_result|评分项分数汇总（来自评分项信息表SCOREITEM）。以逗号分开，第一个是实验1的成绩（总分），所有评分项分数的和；第二个开始是评分项的得分，有多少个评分项就有多少个得分，比如：“99,19,30,20,30”表示一共批改了4次，4次的成绩分别是19,30,20,30，4次的总分是99|
  |test_result|本实验成绩，可以为空，为空表示没有批改，没有批改的实验不入平均成绩，为0分则要计入平均成绩，所以成绩为空和为0是不一样的。|
  |general_evaluation|综合评价，将所有评分项评价集合起来，可以为空|
  |update_date|本实验老师的批改日期，可以为空|


