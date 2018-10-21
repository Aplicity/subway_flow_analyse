# subway_flow_analyse
地铁流量分析

## 英文版本
### Section 1: Data Analysis
 * Please answer the questions below and show your work in an accompanying notebook:

 * What is the total number of entries across the subway system for August 1, 2017? 

 * If we define traffic as the sum of the entry & exit count, what turnstile had the most traffic on August 1, 2017? 

 * Which station had the highest average number of entries between midnight and 4am on Fridays in July 2017? 

 * If we compare the month of July 2016 to the month of July 2017, what station saw the highest relative traffic growth? 

 * From July 2016 through July 2017, what date had the least traffic? 

### Section 2: Modeling
 * In this section, we ask you to describe your thought process in building a model to forecast the future exit count for any  given turnstile device and station. We encourage you to describe a model that can be interpreted using a plain English logical explanation, as opposed to a black-box approach.

 * Please describe the features you would construct to build your model. Please explain what each feature captures about the data and why this is the best way to capture it. 

 * Please describe the model you would propose to develop, and please explain why you prefer this model over alternatives. Please use plain English to describe how your predictive model would work, as if your reader didn't have a data science background and could only understand basic logical principles. 
 
### DataSet Download
[Download Link](https://pan.baidu.com/s/117URQQDkfpPd15CpuS7LBA)

## Data Describe
* C/A      = Control Area (A002)
 * UNIT     = Remote Unit for a station (R051)
 * SCP      = Subunit Channel Position represents an specific address for a device (02-00-00)
 * STATION  = Represents the station name the device is located at
 * LINENAME = Represents all train lines that can be boarded at this station
           Normally lines are represented by one character.  LINENAME 456NQR repersents train server for 4, 5, 6, N, Q, and R trains.
 * DIVISION = Represents the Line originally the station belonged to BMT, IRT, or IND   
 * DATE     = Represents the date (MM-DD-YY)
 * TIME     = Represents the time (hh:mm:ss) for a scheduled audit event
 * DESC     = Represent the "REGULAR" scheduled audit event (Normally occurs every 4 hours)
           1. Audits may occur more that 4 hours due to planning, or troubleshooting activities. 
           2. Additionally, there may be a "RECOVR AUD" entry: This refers to a missed audit that was recovered. 
 * ENTRIES  = The comulative entry register value for a device
 * EXIST    = The cumulative exit register value for a device



### Example:
The data below shows the entry/exit register values for one turnstile at control area (A002) from 09/27/14 at 00:00 hours to 09/29/14 at 00:00 hours

C/A,UNIT,SCP,STATION,LINENAME,DIVISION,DATE,TIME,DESC,ENTRIES,EXITS
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,00:00:00,REGULAR,0004800073,0001629137,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,04:00:00,REGULAR,0004800125,0001629149,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,08:00:00,REGULAR,0004800146,0001629162,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,12:00:00,REGULAR,0004800264,0001629264,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,16:00:00,REGULAR,0004800523,0001629328,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,20:00:00,REGULAR,0004800924,0001629371,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,00:00:00,REGULAR,0004801104,0001629395,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,04:00:00,REGULAR,0004801149,0001629402,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,08:00:00,REGULAR,0004801168,0001629414,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,12:00:00,REGULAR,0004801304,0001629463,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,16:00:00,REGULAR,0004801463,0001629521,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,20:00:00,REGULAR,0004801737,0001629555,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-29-14,00:00:00,REGULAR,0004801836,0001629574,



## 中文版本
### 数据分析
请回答以下问题，并在notebook中显示您的工作：
 * 2017年8月1日地铁系统的参赛作品总数是多少？

 * 如果我们将流量定义为进入和退出计数的总和，那么2017年8月1日哪个旋转门的流量最大？

 * 2017年7月的星期五午夜到凌晨4点之间哪个电台的平均入场次数最高？

 * 如果我们将2016年7月份与2017年7月份进行比较，那么哪个站点的相对流量增长率最高？

 * 从2016年7月到2017年7月，哪个日期的流量最少？
 
 ### 建模
 * 在本节中，我们要求您描述构建模型的思考过程，以预测任何给定的旋转门装置和站点的未来出口计数。我们鼓励您描述一个可以使用简单的英语逻辑解释来解释的模型，而不是黑盒方法。

 * 请描述您为构建模型而构建的功能。请解释每个功能捕获的有关数据的内容以及为什么这是捕获数据的最佳方式。

 * 请描述您打算开发的模型，并解释为什么您更喜欢这种模型而非替代品。请使用简单的英语来描述您的预测模型如何工作，就像您的读者没有数据科学背景并且只能理解基本逻辑原理一样。

 
### 数据下载
由于数据过大，压缩后的文件公300M左右，请到百度云下载：[下载链接](https://pan.baidu.com/s/117URQQDkfpPd15CpuS7LBA)

### 数据描述
 * C / A =控制区域（A002）
 * UNIT =工作站的远程单元（R051）
 * SCP =子单元通道位置代表设备的特定地址（02-00-00）
 * STATION =表示设备所在的电台名称
 * LINENAME =代表可在此车站登上的所有列车线路
           通常，线条由一个字符表示。 LINENAME 456NQR repersents为4,5,6，N，Q和R列车提供服务。
 * DIVISION =表示该线路最初属于BMT，IRT或IND
 * DATE =代表日期（MM-DD-YY）
 * TIME =表示计划的审核事件的时间（hh：mm：ss）
 * DESC =代表“常规”预定审核事件（通常每4小时发生一次）
           1.由于计划或故障排除活动，审核可能会超过4小时。
           2.此外，可能存在“RECOVR AUD”条目：这是指已恢复的错过的审核。
 * ENTRIES =设备的输入条目寄存器值
 * EXIST =设备的累计退出寄存器值



#### 示例：
以下数据显示了2014年9月27日00:00至2014年9月29日00:00时控制区域（A002）的一个旋转门的进/出寄存器值

C/A,UNIT,SCP,STATION,LINENAME,DIVISION,DATE,TIME,DESC,ENTRIES,EXITS
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,00:00:00,REGULAR,0004800073,0001629137,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,04:00:00,REGULAR,0004800125,0001629149,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,08:00:00,REGULAR,0004800146,0001629162,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,12:00:00,REGULAR,0004800264,0001629264,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,16:00:00,REGULAR,0004800523,0001629328,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-27-14,20:00:00,REGULAR,0004800924,0001629371,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,00:00:00,REGULAR,0004801104,0001629395,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,04:00:00,REGULAR,0004801149,0001629402,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,08:00:00,REGULAR,0004801168,0001629414,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,12:00:00,REGULAR,0004801304,0001629463,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,16:00:00,REGULAR,0004801463,0001629521,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-28-14,20:00:00,REGULAR,0004801737,0001629555,
A002,R051,02-00-00,LEXINGTON AVE,456NQR,BMT,09-29-14,00:00:00,REGULAR,0004801836,0001629574,
