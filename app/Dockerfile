FROM python:3.6
ENV PYTHONUNBUFFERED 1

RUN mkdir /code
WORKDIR /code

# 先に requirements.txt のみをコピー
ADD requirements.txt /code/
# その後、pip install を実行
RUN pip install -r requirements.txt
# 最後に、残りのファイルとディレクトリをコピー
ADD . /code/

# Node.js & npmのインストール
RUN apt update && apt install -y nodejs npm \
    && npm install -g n \
    && n 14 \
    && apt purge -y nodejs npm

# package.jsonの中身をインストール
RUN mkdir -p node_modules && npm install
