# Tutorial

Mount s3 bucket on centos 6


### Step 0
Remove fuse and setup libs
```sh
# yum erase fuse
# yum install gcc libstdc++-devel gcc-c++ curl-devel libxml2-devel openssl-devel mailcap automake fuse-devel git libcurl-devel libxml2-devel make
```

### Step 1
Download fuse


### Step 2
Download  s3fs-fuse


### Step 3
Install fuse
```sh
# ./configure
# make -j8
# make install
```

### Step 4

add /usr/local/lib to /etc/ld.so.conf and/or run ldconfig.
And export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig

```sh
# echo /usr/local/lib >> /etc/ld.so.conf
# ldconfig
# export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig
```
### Step 5

Install s3fs-fuse

```sh
# ./autogen.sh
# ./configure
# make && make install
```

### Step 6
```sh
# echo AWS_ACCESS_KEY_ID:AWS_SECRET_ACCESS_KEY > /etc/passwd-s3fs
# chmod 600 /etc/passwd-s3fs
```


### Step 7
```sh
mkdir /tmp/cache; mkdir /mnt/s3mnt ;  chmod 777 /tmp/cache /mnt/s3mnt
```

### Step 8
test
```sh
# s3fs  bucket-e9f4f482  /mnt/s3mnt
```

