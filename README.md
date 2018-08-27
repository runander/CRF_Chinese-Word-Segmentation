# 利用CRF条件随机场进行中文分词
使用Bakeoff 2005微软亚洲研究院提供的中文分词语料进行训练，公开的数据在[这里](http://sighan.cs.uchicago.edu/bakeoff2005/)。在我爱自然语言上看到了这篇文章，自己动手进行了实践，使用CRF++ 0.58工具，训练大约用了2个多小时，最终在Bakeoff 2005数据集上测试，准确率0.964，召回率0.965。 
## 一.准备工作 
请下载上面的数据集icwb2-data.zip，在系统中安装CRF++ 0.58。
## 二、数据格式处理
在文件夹/icwb2-data/training/找到msr_training.utf8，运行programs中提供的```Make_crf_train_data.py```，将数据变成Crf所读取的格式。
## 三、开始训练
在终端中输入```crf_learn -f 3 -c 4.0 template msr_training.tagging4crf.utf8 crf_model```，此命令将进行训练。重要说明：template存在与CRF++文件夹example/seg/中，msr_training.tagging4crf.utf8是上一步我们产出的文件，训练结束后会生成crf_model模型文件。
