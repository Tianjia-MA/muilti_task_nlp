# muilti_task_nlp
0、任务完成流程
   1-租用GPU上完成三个任务的模型训练并生成结果
   GPU: RTX 2080Ti （nvidia-smi)
   环境：Cuda 10， Pytorch 10.0
   2-本地环境配置Docker提交训练结果
   
1、GPU跑Bert预训练模型
   1-目录结构
   2-处理流程
     1）官网上下载Bert预训练权重：（）三部分，放在
     2）分别下载三个任务的数据集，放在/tianchi_datasets下
     3）训练集和测试集分开：
        python ./generate_data.py
     4）训练模型，一个epoch：
        python ./train.py
        会保存验证集上平均f1分数最高的模型到 ./saved_best.pt
     5）用训练好的模型 ./saved_best.pt 生成结果：
        python ./inference.py
     6）打包预测结果：
        zip -r ./result.zip ./*.json
        
2、Docker使用步骤
