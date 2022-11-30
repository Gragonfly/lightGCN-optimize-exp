# lightGCN-optimize-exp

###文件介绍：
    1. LightGCN-PyTorch-master，未改进的模型
    2.mlp，多层感知机表示词嵌入改进模型
    3.sigmoid，层际嵌入改进模型
    4.cat，全连接嵌入改进模型

###如何运行：
    运行未改进的模型，使用如下指令：
        cd LightGCN-PyTorch-master/code
        python main.py --decay=1e-4 --lr=0.001 --layer=3 --seed=2020 --dataset="gowalla" --topks="[20]" --recdim=64
    运行多层感知机表示词嵌入改进模型
        使用mlp文件夹下的model.py替换LightGCN-PyTorch-master/code下的model.py
        cd LightGCN-PyTorch-master/code
        python main.py --decay=1e-4 --lr=0.001 --layer=3 --seed=2020 --dataset="gowalla" --topks="[20]" --recdim=64
    运行层级词嵌入改进模型
        使用sigmoid文件夹下的model.py替换LightGCN-PyTorch-master/code下的model.py
        cd LightGCN-PyTorch-master/code
        python main.py --decay=1e-4 --lr=0.001 --layer=3 --seed=2020 --dataset="gowalla" --topks="[20]" --recdim=64
    运行全连接嵌入改进模型
        使用cat文件夹下的model.py替换LightGCN-PyTorch-master/code下的model.py
        cd LightGCN-PyTorch-master/code
        python main.py --decay=1e-4 --lr=0.001 --layer=3 --seed=2020 --dataset="gowalla" --topks="[20]" --recdim=64

###代码改进部分：
    多层感知机表示词嵌入改进模型
        创建新类permute_linear，表示多层感知机并使用sigmoid函数激活
        在训练同时对mlp中的参数进行训练
    层级词嵌入改进模型
        在层之间添加sigmoid激活函数
    全连接嵌入改进模型
        在最终嵌入表示时不使用均值而使用全连接

    维度改进仅需改变运行命令的recdim的参数即可