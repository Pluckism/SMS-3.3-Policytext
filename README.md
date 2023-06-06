# SMS-3.3-Policytext
SMS-3.3-政策文本版
按下win+R键，输入cmd，然后依次输入以下代码：

更换为清华源：
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

查看目前的pip下载源：
pip config get global.index-url
*********************************************************

店家搭建好环境后：
1.请店家安装jupyter插件，并成功运行

2.请在系统环境变量中修改PPNLP-HOME路径为E:\workspace

3.在vscode中进行以下验证：
from paddlenlp import Taskflow
tag = Taskflow('pos_tagging', mode='accurate', batch_size=32)


*****若成功运行，即能顺利使用SMS 3.1，且后续使用无需重复搭建环境*****
python 3.7.8

*****************************************************************************
from sklearn.feature_extraction.text import CountVectorizer

import TfidfTransformer

from paddlenlp import Taskflow   （CPU版，paddlenlp模型安装到E:\workspace路径）

import os

import re

import pandas as pd

import numpy as np

from gensim.models import word2vec

from gensim.models.word2vec import Word2Vec

（请店家帮忙安装vscode编辑器，并配置好python 3.7.8，jupyter）


***************************Maymon‘s environment********************************
Package                  Version
------------------------ ----------
aiofiles                 23.1.0
aiohttp                  3.8.4
aiosignal                1.3.1
allennlp                 2.10.1
altair                   4.2.2
anyio                    3.6.2
argon2-cffi              21.3.0
argon2-cffi-bindings     21.2.0
astor                    0.8.1
async-timeout            4.0.2
asynctest                0.13.0
attrdict                 2.0.1
attrs                    22.2.0
Babel                    2.11.0
backcall                 0.2.0
base58                   2.1.1
bce-python-sdk           0.8.79
bcrypt                   4.0.1
beautifulsoup4           4.11.2
bleach                   6.0.0
blis                     0.7.9
boto3                    1.26.74
botocore                 1.29.74
bottle                   0.12.23
Brotli                   1.0.9
cached-path              1.1.6
cachetools               5.3.0
catalogue                2.0.8
certifi                  2022.12.7
cffi                     1.15.1
chardet                  5.1.0
charset-normalizer       3.0.1
click                    8.1.3
cloudpickle              2.2.1
cmdstanpy                1.1.0
colorama                 0.4.6
colorlog                 6.7.0
common                   0.1.2
commonmark               0.9.1
convertdate              2.4.0
cryptography             39.0.1
cycler                   0.11.0
cymem                    2.0.7
Cython                   0.29.28
dask                     2022.2.0
data                     0.4
datasets                 2.9.0
debugpy                  1.6.6
decorator                5.1.1
defusedxml               0.7.1
Deprecated               1.2.13
dill                     0.3.4
distributed              2022.2.0
docker-pycreds           0.4.0
dual                     0.0.10
dynamo3                  0.4.10
easydict                 1.10
entrypoints              0.4
ephem                    4.1.4
et-xmlfile               1.1.0
exceptiongroup           1.1.0
fairscale                0.4.6
fastapi                  0.92.0
fastjsonschema           2.16.2
featuretools             1.11.1
ffmpeg                   1.4
ffmpeg-python            0.2.0
ffmpy                    0.3.0
filelock                 3.7.1
Flask                    2.2.3
Flask-Babel              2.0.0
flywheel                 0.5.4
fonttools                4.38.0
frozenlist               1.3.3
fsspec                   2023.1.0
funcsigs                 1.0.2
future                   0.18.3
gensim                   4.2.0
gevent                   22.10.2
geventhttpclient         2.0.2
gitdb                    4.0.10
GitPython                3.1.31
google-api-core          2.11.0
google-auth              2.16.1
google-cloud-core        2.3.2
google-cloud-storage     2.7.0
google-crc32c            1.5.0
google-resumable-media   2.4.1
googleapis-common-protos 1.58.0
gradio                   3.18.0
greenlet                 2.0.2
grpcio                   1.51.3
h11                      0.14.0
h5py                     3.8.0
HeapDict                 1.0.1
hijri-converter          2.2.4
holidays                 0.19
httpcore                 0.16.3
httpx                    0.23.3
huggingface-hub          0.12.1
hypernets                0.2.5.7
hyperts                  0.2.0
idna                     3.4
importlib-metadata       6.0.0
importlib-resources      5.12.0
iniconfig                2.0.0
ipykernel                6.16.2
ipython                  7.34.0
ipython-genutils         0.2.0
ipywidgets               8.0.4
itsdangerous             2.1.2
jedi                     0.18.2
jieba                    0.42.1
Jinja2                   3.1.2
jmespath                 1.0.1
joblib                   1.2.0
jsonpickle               3.0.1
jsonschema               4.17.3
jupyter                  1.0.0
jupyter_client           7.4.9
jupyter-console          6.5.1
jupyter_core             4.12.0
jupyter-server           1.23.6
jupyterlab-pygments      0.2.2
jupyterlab-widgets       3.0.5
kiwisolver               1.4.4
korean-lunar-calendar    0.3.1
langcodes                3.3.0
lightgbm                 3.3.5
linkify-it-py            1.0.3
llvmlite                 0.39.1
lmdb                     1.4.0
locket                   1.0.0
LunarCalendar            0.0.9
markdown-it-py           2.1.0
MarkupSafe               2.1.2
matplotlib               3.5.3
matplotlib-inline        0.1.6
mdit-py-plugins          0.3.4
mdurl                    0.1.2
mistune                  2.0.5
more-itertools           9.0.0
mpmath                   1.2.1
msgpack                  1.0.4
multidict                6.0.4
multiprocess             0.70.12.2
murmurhash               1.0.9
nbclassic                0.5.2
nbclient                 0.7.2
nbconvert                7.2.9
nbformat                 5.7.3
nest-asyncio             1.5.6
networks                 0.3.7
networkx                 2.6.3
nltk                     3.8.1
notebook                 6.5.2
notebook_shim            0.2.2
numba                    0.56.4
numpy                    1.21.6
onnx                     1.8.0
openai                   0.27.0
openai-whisper           20230306
opencv-python            4.7.0.68
openpyxl                 3.1.1
opt-einsum               3.3.0
orjson                   3.8.6
packaging                23.0
paddle-bfloat            0.1.7
paddle2onnx              1.0.5
paddlefsl                1.1.0
paddlehub                2.3.1
paddlenlp                2.4.0
paddlepaddle             2.4.2
pandas                   1.3.5
pandocfilters            1.5.0
paramiko                 3.0.0
parso                    0.8.3
partd                    1.3.0
pathtools                0.1.2
pathy                    0.10.1
patsy                    0.5.3
pdfminer                 20191125
pdfminer.six             20221105
pdfplumber               0.8.0
peewee                   3.15.4
phrasetree               0.0.8
pickleshare              0.7.5
Pillow                   9.4.0
pip                      23.0.1
pkgutil_resolve_name     1.3.10
pluggy                   1.0.0
preshed                  3.0.8
prettytable              3.6.0
prometheus-client        0.16.0
promise                  2.3
prompt-toolkit           3.0.36
prophet                  1.1.2
protobuf                 3.20.0
prox                     0.0.17
psutil                   5.9.4
pyarrow                  11.0.0
pyasn1                   0.4.8
pyasn1-modules           0.2.8
pycparser                2.21
pycryptodome             3.17
pydantic                 1.8.2
pydub                    0.25.1
Pygments                 2.14.0
PyMeeus                  0.5.12
PyNaCl                   1.5.0
pynvml                   11.5.0
pyparsing                3.0.9
PyPDF2                   3.0.1
pyrsistent               0.19.3
PySocks                  1.7.1
pytest                   7.2.1
python-dateutil          2.8.2
python-geoip-python3     1.3
python-multipart         0.0.5
python-rapidjson         1.9
pytz                     2022.7.1
pywin32                  305
pywinpty                 2.0.10
PyYAML                   6.0
pyzmq                    25.0.0
qtconsole                5.4.0
QtPy                     2.3.0
rank-bm25                0.2.2
rarfile                  4.0
regex                    2022.10.31
requests                 2.28.2
responses                0.18.0
rfc3986                  1.5.0
rich                     12.6.0
rsa                      4.9
s3transfer               0.6.0
sacremoses               0.0.53
scikit-learn             1.0.2
scipy                    1.7.3
seaborn                  0.12.2
Send2Trash               1.8.0
sentencepiece            0.1.97
sentry-sdk               1.16.0
seqeval                  1.2.2
setproctitle             1.3.2
setuptools               47.1.0
shortuuid                1.0.11
six                      1.16.0
sktime                   0.16.1
smart-open               6.3.0
smmap                    5.0.0
sniffio                  1.3.0
sortedcontainers         2.4.0
soupsieve                2.4
spacy                    3.3.2
spacy-legacy             3.0.12
spacy-loggers            1.0.4
srsly                    2.4.6
starlette                0.25.0
statsmodels              0.13.5
sympy                    1.10.1
tblib                    1.7.0
tensorboardX             2.6
termcolor                1.1.0
terminado                0.17.1
thinc                    8.0.17
threadpoolctl            3.1.0
tight                    0.1.0
tinycss2                 1.2.1
tokenizers               0.11.6
tomli                    2.0.1
toolz                    0.12.0
toposort                 1.5
torch                    1.12.1
torchaudio               0.12.1
torchvision              0.13.1
tornado                  6.2
tqdm                     4.64.1
traitlets                5.9.0
transformers             4.20.1
tritonclient             2.31.0
typer                    0.4.2
typing_extensions        4.1.1
uc-micro-py              1.0.1
urllib3                  1.26.14
uvicorn                  0.20.0
visualdl                 2.4.2
Wand                     0.6.11
wandb                    0.12.21
wasabi                   0.10.1
wcwidth                  0.2.6
webencodings             0.5.1
websocket-client         1.5.1
websockets               10.4
Werkzeug                 2.2.3
wheel                    0.38.4
whisper                  1.1.10
widgetsnbextension       4.0.5
woodwork                 0.16.4
wrapt                    1.14.1
x2paddle                 1.4.0
XlsxWriter               3.0.8
xlwt                     1.3.0
xxhash                   3.2.0
yarl                     1.8.2
zhon                     1.1.5
zict                     2.2.0
zipp                     3.14.0
zope.event               4.6
zope.interface           5.5.2
