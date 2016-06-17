# Tutorial
Mount s3 bucket on centos 6 


Step 0
yum erase fuse
Step 1
Download fuse
Step 2
Download  s3fs-fuse
Step 3
Install fuse
# ./configure
# make -j8
# make install
Step 4
add /usr/local/lib to /etc/ld.so.conf and/or run ldconfig
export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig
modprobe fuse
Step 5
Install s3fs-fuse
# ./autogen.sh
# ./configure
# make && make install
Step 6
# echo AWS_ACCESS_KEY_ID:AWS_SECRET_ACCESS_KEY > /etc/passwd-s3fs
# chmod 600 /etc/passwd-s3fs
Step 7
# mkdir /tmp/cache; mkdir /mnt/s3mnt ;  chmod 777 /tmp/cache /mnt/s3mnt
Step 8
Test
# s3fs  bucket-e9f4f482  /s3mnt

