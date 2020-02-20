# 异常检测数据集
**************

## Genesis Demonstrator Data
### 数据集描述
1.  该数据集来自一种便携式取放演示器，使用气罐为所有抓取和存储单元提供动力。其记录了5（+4）个连续信号，13个离散信号和1个Unix时间戳。

### 数据集信息
该数据集包含两个数据集
1.  第一个数据集包含文件**Genesis StateMachineLabels.csv**和**Genesis AnomalyLabels.csv**。

- 文件包含每隔50毫秒通过OPC DA服务器进行的16220次观测值。缺失值和零差异列已经删除。

- **Genesis_StateMachineLabel.csv**中的Label列表示PLC代码的内部状态机。状态描述如下：


  | 状态 | 状态描述| 
  |  :----:  |  :----:  | 
  | 0 | Idle |
  | 1 | Homing |  
  | 2 | AvoidStorage |   
  | 3 | ActivateStorage |
  | 4 | ToStorage |
  | 5 | CloseGripper |
  | 6 | ToSensor |
  | 7 | ToBox |
  | 8 | OpenGripper |
  
- 在**Genesis_AnomalyLabels.csv**文件中，对异常标签进行了手动注释，仅模拟了一种类型的异常。异常描述如下：
  
  | 异常 | 异常描述| 
  |  :----:  |  :----:  | 
  | 0 | 无异常(No anomaly) |
  | 1 | 线性驱动器卡住/倾斜(Linear drive jammed / tilted) |  
  | 2 | 线性驱动器断开并纠正累积滞后误差(Linear drive breaks free and corrects accumulated lag error) | 
  
2.  第二个数据集包含文件**Genesis normal.csv**，**Genesis lineardrive.csv**，**Genesis_pressure.csv**。

- 该数据集包含未标记的数据（包含正常运行和错误运行的数据）。

- 在**Genesis_normal.csv**文件中，演示程序按预期工作，没有任何故障或限制。可以将其与其他文件进行比较，以进行预测性维护或异常检测。

- 在**Genesis_lineardrive.csv**文件中，随着时间的推移，线性驱动器受到了轻微损害，因此Genesis Demonstrator无法正常工作。该文件可用于预测性维护或异常检测。

- 在**Genesis_pressure.csv**文件中，气压随着时间的推移而降低，因此Genesis Demonstrator无法正常工作。该文件可用于预测性维护或异常检测。

### 数据集来源：[Genesis Demonstrator Data](https://www.kaggle.com/inIT-OWL/genesis-demonstrator-data-for-machine-learning)


## 轴承数据
### 数据集描述
1.  轴承是在机械设备中具有广泛应用的关键部件之一。由于过载，疲劳，磨损，腐蚀等原因，轴承在机器操作过程中容易损坏。一般来说，早期的轴承弱故障是复杂的，难以检测。因此，轴承状态的监测和分析非常重要，它可以发现轴承的早期弱故障，防止故障造成损失。而在所有类型的轴承故障诊断方法中，振动信号分析是最主要和有用的工具之一。

2.  该数据集是一个真实轴承振动信号数据集。轴承有3种故障：外圈故障，内圈故障，滚珠故障，外加正常的工作状态。如下表所示，结合轴承的3种直径（直径1,直径2,直径3），轴承的工作状态有10类：

|        | 外圈故障| 内圈故障 | 滚珠故障  | 正常 |
| :----: | :----:| :------:| :-----:  | :---:|
| 直径 1  | 1     |    2     |    3    |  0  |
| 直径 2  | 4     |    5     |    6    |  0  |
| 直径 3  | 7     |    8     |    9    |  0  |

### 数据集信息
1.  train.csv，训练集数据，1到6000为按时间序列连续采样的振动信号数值，每行数据是一个样本，共792条数据，第一列id字段为样本编号，最后一列label字段为标签数据，即轴承的工作状态，用数字0到9表示。

2.  test_data.csv，测试集数据，共528条数据，除无label字段外，其他字段同训练集。
> 每行数据除去id和label后是轴承一段时间的振动信号数据。
### 数据集来源：DC竞赛-轴承故障检测训练赛，[竞赛链接](https://www.dcjingsai.com/common/cmpt/%E8%BD%B4%E6%89%BF%E6%95%85%E9%9A%9C%E6%A3%80%E6%B5%8B%E8%AE%AD%E7%BB%83%E8%B5%9B_%E7%AB%9E%E8%B5%9B%E4%BF%A1%E6%81%AF.html)


## 可穿戴传感器健康老年人动作识别
### 数据集描述

1.  该数据集包含14位年龄在66至86岁之间的健康老年人的运动数据，这些运动数据是使用无电池的可穿戴式传感器在胸骨水平的衣服上进行的。由于使用了无源传感器，因 此数据稀疏且嘈杂。

2.  参与者被分配到两个临床房间设置（S1和S2）。S1（Room1）的设置使用房间周围的4个RFID阅读器天线（在天花板上一个，在墙壁上3个）来收集数据，而房间S2（Room2）的设置使用3个RFID阅读器天线（在天花板上两个）一层，另一层在墙壁上）以收集运动数据。

3.  参与者可以在房建类进行如下活动：走到椅子上（walking to the chair），坐在椅子上（sitting on the chair），从椅子上下来（getting off the chair），走向床（walking to bed），躺在床上（lying on bed），下床（getting off the bed），以及走到门口（walking to the door）。

4.  监测数据有四种可能的标签（四种动作）：坐在床上（sitting on bed），坐在椅子上（sitting on chair），躺在床上（lying on bed），以及走动（Ambulating）。
> 该数据集不是专门的异常检测数据集。如果将一种动作作为异常动作，而其他三种作为正常动作，可作为异常检测任务。

### 数据集信息
该文件的内容如下：

| 列数 | 含义| 
|  :----:  |  :----:  | 
| 1 | 以秒为单位的时间戳 |  
| 2 | 前轴的G加速度读数 |   
| 3 | 垂直轴的G加速度读数 |
| 4 | 横轴的G加速度读数 |
| 5 | 天线读数传感器的ID |
| 6 | 接收信号强度指示器（RSSI） |
| 7 | 阶段 |
| 8 | 频率 |
| 9 | 活动标签；1：坐在床上；2：坐在椅子上；3：躺着；4：移动 |

### 数据来源：来自于[Mad Net](http://mad-net.org:8765/index.html?t=0.1629550266458497)数据平台，[可穿戴传感器健康老年人动作识别](http://mad-net.org:8765/explore.html?t=0.5831516555847212)数据集。


## Satellite
### 数据集描述

1.  该数据集来自于陆地卫星（Statlog），是一个多类分类**点数据集**。
2.  数据集中最小的三个类别（2，4，5）被作为异常数据类别，其余作为正常数据类别。

### 数据信息

| 数据量 | 数据维度| 异常比例 | 
| :----: | :----:| :------:| 
| 6435 | 36 | 2036 (32%)| 

### 数据来源：来自[UCI数据库](https://archive.ics.uci.edu/ml/index.php)的[Statlog (Landsat Satellite)](https://archive.ics.uci.edu/ml/datasets/Statlog+%28Landsat+Satellite%29)数据集。

## Shuttle
### 数据集描述

1.  该数据集来自陆地卫星（Statlog），是一个多类分类**点数据集**，维度为9.
2.  数据集中最小的五个类别（2，3，5，6，7）被作为异常数据类别，类别1作为正常数据类别，类别4被丢弃。

### 数据信息

| 数据量 | 数据维度| 异常比例 | 
| :----: | :----:| :------:| 
| 49097 | 9 | 3511 (7%) | 

### 数据来源：来自[UCI数据库](https://archive.ics.uci.edu/ml/index.php)的[Statlog (Shuttle)](https://archive.ics.uci.edu/ml/datasets/Statlog+%28Shuttle%29)数据集。

## Mammography
### 数据集描述

1.  乳腺摄影数据集（[Woods等，1993](https://www.worldscientific.com/doi/abs/10.1142/S0218001493000698)）由 [Aleksandar Lazarevic](https://www-users.cs.umn.edu/~lazar027/)提供。
2.  该数据集有11183个样本，其中260个钙化。将钙化的样本视为异常样本，非钙化样本视为正常样本

### 数据信息

| 数据量 | 数据维度| 异常比例 | 
| :----: | :----:| :------:| 
| 11183 | 6 | 260 (2.32%) | 

### 数据来源：可在[openML](https://www.openml.org/d/310)中获得













