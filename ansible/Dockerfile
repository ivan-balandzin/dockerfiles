FROM sbeliakou/centos

RUN yum update -y && \
    yum install -y python-pip python-devel && \
    yum install -y gcc openssl-devel && \
    yum install -y rsync openssh-clients && \
    yum clean all

RUN pip install -U pip setuptools boto boto3 requests && \
    pip install ansible==2.2.1 requests termcolor

ADD ansible.cfg /etc/ansible/ansible.cfg

ENV ANSIBLE_LOCAL_TEMP=/tmp
ENV ANSIBLE_FORCE_COLOR=true
ENV PYTHONUNBUFFERED=1

CMD ansible --version
