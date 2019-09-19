sudo su
apt install software-properties-common
add-apt-repository ppa:jonathonf/gcc-7.1
apt update
apt upgrade
apt install git build-essential cmake libuv1-dev libssl-dev libmicrohttpd-dev gcc-7 g++-7
reboot

git clone https://github.com/xmrig/xmrig.git
cd xmrig
mkdir build
cd build
cmake .. -DCMAKE_C_COMPILER=gcc-7 -DCMAKE_CXX_COMPILER=g++-7
make
cat /sys/kernel/mm/transparent_hugepage/enabled
sysctl -w vm.nr_hugepages=8
./xmrig -a cryptonight -o pool.supportxmr.com:5555  --user=4ArjTK6VcemQRePxhxGNK2HBCjq639gtiEwfLsUm2QcscgAmaobGHWwF7ip6abxphLYx4kvvbswvT16uMBU2N9aeNeh9hyx -p motel177:alexisdavid_2016@hotmail.com -t 
