FROM continuumio/miniconda3:4.5.12
MAINTAINER marvinpan <pantj@investoday.com.cn>

RUN conda install pandas pymysql scikit-learn tqdm keras \
    && conda install pytorch-cpu torchvision-cpu -c pytorch \
    && pip install xgboost --index https://pypi.mirrors.ustc.edu.cn/simple/ 

