FROM python:alpine
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
RUN pip install Flask
COPY rng.py /
CMD ["python", "rng.py"]
EXPOSE 80
