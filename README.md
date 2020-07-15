# Install OpenSSL
https://gist.github.com/ryzy/1d22a3de8798732c2541

wget -O /tmp/openssl.tgz https://www.openssl.org/source/openssl-1.1.1g.tar.gz
tar -zxf /tmp/openssl.tgz -C /tmp
cd /tmp/openssl-*
./config --prefix=/usr --openssldir=/etc/ssl --libdir=lib no-shared zlib-dynamic
make
make install_sw


# install HAProxy
https://upcloud.com/community/tutorials/haproxy-load-balancer-centos/

wget http://www.haproxy.org/download/2.0/src/haproxy-2.0.7.tar.gz -O /tmp/haproxy-2.0.7.tar.gz
make TARGET=linux-glibc ADDLIB=-lpthread USE_OPENSSL=1  USE_ZLIB=1 USE_PCRE=1