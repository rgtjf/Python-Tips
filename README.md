# Python-Tips


## 1.python2 和 python3 共享

```Shell
conda create --name py27 python=2.7 anaconda
conda create --name py35 python=3.5 anaconda
```
切换环境
```Shell
activate <env name> (Windows)
source activate <env name> (Linux)
```

## 2. pickle from python2 to python3

```Error
  File "H:\fixers - 3.4\addressfixer - 3.4\trunk\lib\address\address_generic.py"
, line 382, in read_ref_files
    d = pickle.load(open(mshelffile, 'rb'))
UnicodeDecodeError: 'ascii' codec can't decode byte 0xe2 in position 1: ordinal
not in range(128)
```
Solve Solution
```Python
with open(mshelffile, 'rb') as f:
    d = pickle.load(f, encoding='latin1') 
```

## 3. download file from Internet in Python

```python
import urllib.request, urllib.parse, urllib.error

origin = 'https://raw.githubusercontent.com/brmson/dataset-sts/master/data/para/msr/msr-para-train.tsv'
dataset = 'msr-para-train.tsv'
print('Downloading data from %s' % origin)
urllib.request.urlretrieve(origin, dataset)
```


## 4. pyCharm (2016.1) 添加 python 路径
![tips4-0](figs/tips4-0.png)

## 5. Add Python Path In Linux
1. http://stackoverflow.com/questions/3402168/permanently-add-a-directory-to-pythonpath
2. 
```
vi ~/.bashrc
export PYTHONPATH=${PYTHONPATH}:path1:path2
```

## 6. Git Operation
```git
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/rgtjf/test.git
git push -u origin master
```