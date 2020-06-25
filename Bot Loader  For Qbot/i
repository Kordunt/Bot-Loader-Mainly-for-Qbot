#!/bin/bash
yum install cpan wget curl glibc.i686 -y
cpan force install Parallel::ForkManager
cpan force install IO::Socket
cpan force install IO::Select
yum install gcc php-devel php-pear libssh2 libssh2-devel libpcap -y
pecl install -f ssh2
touch /etc/php.d/ssh2.ini
echo extension=ssh2.so > /etc/php.d/ssh2.ini
cpan force install Net::SSH2
yum update -y
yum install gcc cmake gmp gmp-devel libpcap-devel gengetopt byacc flex -y
yum install json-c-doc.noarch json-c.i686 json-c.x86_64 json-c-devel.i686 json-c-devel.x86_64 -y
yum install epel-release -y
yum install gengetopt -y
wget https://github.com/zmap/zmap/archive/v2.1.0.tar.gz
tar -xvf v2.1.0.tar.gz
cd zmap-2.1.0
flex -o "src/lexer.c" --header-file="src/lexer.h" "src/lexer.l"
byacc -d -o "src/parser.c" "src/parser.y"
mkdir /etc/zmap
cp conf/* /etc/zmap
cmake -DENABLE_HARDENING=ON
make
make install
yum install perl-Net-SSH2 -y
yum install perl-Parallel-ForkManager -y