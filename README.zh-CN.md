# MLops-trial · TFX 流水线实验

简体中文

本仓库是一个 MLOps 入门实验：使用 **TensorFlow Extended（TFX）** 搭建一条完整的机器学习流水线，以经典的**企鹅（Penguin）分类数据集**为例，跑通从数据读取、模型训练到模型发布的全过程。

## 流水线组成

| 组件 | 作用 |
| --- | --- |
| `CsvExampleGen` | 读取 CSV 数据，划分训练集与评估集，并转换为 TFRecord 格式 |
| `Trainer` | 调用 `penguin_trainer.py` 中的训练代码训练 Keras 模型 |
| `Pusher` | 将训练好的模型导出为 SavedModel，供部署使用 |

## 项目结构

| 路径 | 说明 |
| --- | --- |
| `Copy_of_penguin_simple.ipynb` | 构建并运行 TFX 流水线的主 Notebook |
| `penguin_trainer.py` | 模型训练模块（供 Trainer 组件调用） |
| `pipelines/penguin-simple/` | 流水线运行产物：数据、训练模型和发布的模型 |
| `metadata/penguin-simple/metadata.db` | ML Metadata（MLMD）元数据库，记录每次运行的血缘信息 |
| `sample_data/` | Google Colab 自带的示例数据 |

## 使用方法

建议在 Google Colab 中打开 `Copy_of_penguin_simple.ipynb`，按顺序运行即可：Notebook 会安装 TFX、下载数据并执行整条流水线。
