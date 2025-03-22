---
date: 2025-02-17
tags:
  - 机器学习
  - 编程
  - Python
注释: Python语言的机器学习工具，文档完善
---
[scikit-learn (sklearn) 官方文档中文版](https://scikitlearn.com.cn/0.21.3/)
[scikit-learn中文社区](https://scikit-learn.org.cn/)
[Sklearn 教程 | 菜鸟教程](https://www.runoob.com/sklearn/sklearn-tutorial.html)
# Sklearn安装
**Sklearn 全称为 scikit-learn**
使用 pip 安装最新版本的 scikit-learn：
``` 
pip install scikit-learn
```
如果你希望安装特定版本的 scikit-learn，可以指定版本号：
```
pip install scikit-learn==1.2.0
```
### 检查安装是否成功
安装完成后，我们可以通过以下代码检查 scikit-learn 是否安装成功：
```python
import sklearn  
print(sklearn.__version__)
```
# Sklearn数据集
## Sklearn数据集API介绍
`sklearn.datasets`
	`load_*`  获取小规模数据集
	`fetch_*` 获取大规模数据集
sklearn小数据集
	`sklearn.datasets.load_iris()`
sklearn大数据集
	`sklearn.datasets.fetch_20newsgroups(data_home=None,subset=‘train’)`
	`subset`:train或者test，all，可选，选择要加载的数据集

```python
from sklearn.datasets import load_iris  
from sklearn.model_selection import train_test_split  
def datasets_demo():  
    """  
    sklearn 数据集使用  
    :return:  
    """    # 获取数据集  
    iris = load_iris()  
    print("鸢尾花数据集:\n", iris)  
    print("查看数据集描述:\n", iris["DESCR"])  
    print("查看特征值的名字:\n", iris.feature_names)  
    print("查看特征值:\n", iris.data, iris.data.shape)  
  
    # 数据集划分  
    x_train, x_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.2)  
    print("训练集的特征值:\n", x_train, x_train.shape)  
    return None  
if __name__ == '__main__':  
    # 代码1：sklearn 数据集使用  
    datasets_demo()
```
