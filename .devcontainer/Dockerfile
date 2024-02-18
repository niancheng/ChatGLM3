FROM hub.okii.com/watch-ai/devcontainer/python:3.12.1-debian12
RUN apt-get update \
    && apt-get -y install cmake pkg-config build-essential \
    # gcc g++ make libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler libboost-all-dev libopenblas-dev liblapack-dev libatlas-base-dev libgflags-dev libgoogle-glog-dev liblmdb-dev \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*
COPY requirements.txt requirements.txt
RUN pip install --disable-pip-version-check --no-cache-dir --retries 50 --trusted-host mirrors.bbkedu.com -i http://mirrors.bbkedu.com/pypi/simple -U -r requirements.txt
RUN curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash \
    && apt-get install git-lfs \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*