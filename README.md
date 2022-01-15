# KG2021pj
2021-2022知识图谱PJ数据集及代码运行方法

---
## Usage
拆分标签词，在代码中更改所用数据集参数
```shell
python get_label_word.py
```

运行
```shell
python main.py --max_epochs=10  --num_workers=8 \
    --model_name_or_path roberta-large \
    --accumulate_grad_batches 4 \
    --batch_size 16 \
    --data_dir dataset/retacred/ \
    --check_val_every_n_epoch 1 \
    --data_class WIKI80 \
    --max_seq_length 256 \
    --model_class RobertaForPrompt \
    --t_lambda 0.001 \
    --wandb \
    --litmodel_class BertLitModel \
    --task_name wiki80 \
    --lr 1e-6 \ 
    --adv 1 \ #adv为0不使用改进方法，为1使用改进方法
```

生成k-shot数据集
```shell
python generate_k_shot.py --data_dir ./dataset --k 8 --dataset retacred --data_file train.txt
python generate_k_shot.py --data_dir ./dataset --k 8 --dataset retacred --data_file val.txt
```
