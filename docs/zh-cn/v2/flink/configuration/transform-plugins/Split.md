## Transform plugin : Split [Flink]

* Author: InterestingLab
* Homepage: https://interestinglab.github.io/waterdrop
* Version: 2.0.0

### Description
定义了一个字符串切割函数，用于在Sql插件对指定字段进行分割。

### Options
| name | type | required | default value |
| --- | --- | --- | --- |
| [separator](#separator-string) | string | no | , |
| [fields](#fields-array) | array | yes | - |


##### separator [string]

指定的分隔符，默认为`,`

##### fields [array]

分割后各个字段的名称

### Examples

```
  #这个只是创建了一个叫split的udf
  Split{
    separator = "#"
    fields = ["name","age"]
  }
  #使用split函数(确认fake表存在)
  sql {
    sql = "select * from (select info,split(info) as info_row from fake) t1"
  }
```