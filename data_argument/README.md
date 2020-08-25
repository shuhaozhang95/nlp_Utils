# Data Augment

记录一下目前为止尝试的几种在NLP方向上的数据增强方法

## 方法论

1. 随机噪声注入  
   基于增删换改的EDA(Easy Data Augment), 同义词更改基于Synonyms, 实际运用最好替换成领域词库  

2. 利用pigeonXT的jupyter notebook标注工具, 利用人工标注解决部分负样本问题    

3. 回译  
   回译用来数据增强，主要是将src语言翻译dst语言，再转换回src语言  
  
   3.1 基于机器翻译模型的回译方法  
       
       目前Notebook里用到的机器翻译模型是由Heisinki开发的  
       
       Reference:  
       1. https://github.com/Helsinki-NLP/Opus-MT  
       2. https://huggingface.co/models
                  
   3.2 基于网络请求的Google翻译进行回译
   
   
## 经验  

1. 回译模型以及更复杂的基于预训练模型的UDA模型，本质上强依赖于文本质量。  
   在实际运用中，语音转写的/获取的文本数据并没有经过人工修正，利用预训练增强的效果并不好。
   
2. 目前预训练模型对抽象概念的文本处理较差  
   实际情况中碰到文本分类（抱怨、嘲讽）等情感词，本质上这些属于情感（高于语义层次）
