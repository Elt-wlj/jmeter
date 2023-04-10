#### jmeter命令行的操作流程
'''  
eg: jmeter -n -t D:\code\doc\presure\create-customer.jmx -l test1.jtl      
分别代表文件路径和日志文件，可以导入到jmeter中下的观察结果树下进行使用。  
eg: jmeter -n -t xx.jmx -l xxx.jtl -e -o xxxxempty_dict    
说明：  
1.xx.jmx是jmeter脚本  
2.xxx.jtl或xxx.csv是生成的文件  
3.xxxxempty_dict是结果转换为的html文件  

'''

#### 使用jmeter保存请求体和相关数据
- 方法一：
  - 1.选择一个空的xml文件，在观察结果数中，填写所有数据写一个文件，在文件名处，写入[路径+ xx.xml]
  - 2.点击 “配置”按钮，在弹窗中，选中“Save As XML” “Save Response Data(XML)” “Save Sampler Data(XML)” 三个复选框
  - 3.点击完成，当在此重新打开时，可以查看之前的请求体和数据相应结果。  
    
 '''
注意：向伊昂保存请求体和响应相数据，文件必须为xml的格式，必须构想save as xml。  
Save Sampler Data（XML）会保存请求的cookie、请求方法、请求体。  
'''  

- 方法二：
  - 1.选择一个空xml文件。
  - 2.配置”按钮，在弹窗中，选中“Save As XML“。
  - 3.点击”完成“。
  - 4.点击 ”测试计划“中的 “函数测试模式”。 
  
'''
注意：xml不能像csv，jtl文件一样生成html报告，需要与ant集成。  
'''

#### jmeter5.1版本后，可在图像化界面生成测试报告
- 1.点击tools,
- 2.点击Generate HTML report
- 3.在弹窗中 
  - 1.第1个“浏览”，选择csv文件或jtl文件 。
  - 2.第2个“浏览” ，选择jmeterbin文件夹中的jmeter.properties或user.properties文件
  - 3.第3个“浏览”， 选择一个空文件夹，然后点击最底部的 “Gererate report” 按钮，就可以生成html到你选择的空文件夹
 
 '''
 注意：如果使用的是无图形界面的jmeter, 可使用：jmeter -g xxxx.jtl -e -o xxxempty_dict  
 
 说明：xxxx.jtl” 可以是你的csv文件也可以是jtl文件， "xxxempty_dict" 就是你把生成html放的空文件夹名称。  
 '''
