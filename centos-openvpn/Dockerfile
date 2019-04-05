FROM centos:centos7.6.1810

RUN yum install epel-release -y
RUN yum install openvpn iptables openssl ca-certificates expect -y

ARG EASYRSAURL='https://github.com/OpenVPN/easy-rsa/releases/download/v3.0.6/EasyRSA-unix-v3.0.6.tgz'
RUN wget -O ~/easyrsa.tgz "$EASYRSAURL" 2>/dev/null || curl -Lo ~/easyrsa.tgz "$EASYRSAURL"

COPY ./openvpn-install.sh /root/openvpn-install.sh
RUN chmod +x /root/openvpn-install.sh

#CMD [ "sh","-x","/root/openvpn-install.sh" ]
CMD [ "/root/openvpn-install.sh" ]