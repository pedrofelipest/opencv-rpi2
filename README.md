# opencv-3-raspberry-pi-2
##Installing OpenCV 3.0 on Raspberry Pi 2

## Open the settings of your RPI

```
sudo raspi-config
```

## Enable camera, ssh and expand filesystem
## Advanced settings expands memory to 256

## Update and Upgrade your RPI

```
sudo apt-get update
sudo apt-get upgrade
```

## Install dependencies

```
sudo apt-get install -y --force-yes autoconf build-essential automake libtool  git cmake pkg-config      \
                                    libpng12-dev libjpeg-dev libtiff5-dev zlib1g-dev libjasper-dev       \
                                    libavcodec-dev libavformat-dev libswscale-dev libv4l-dev             \
                                    libxvidcore-dev libx264-dev libgtk2.0-dev libatlas-base-dev          \
                                    gfortran python2.7-dev python3-dev                                   \
                                    libcurl4-openssl-dev liblog4cplus-1.0-4 liblog4cplus-dev uuid-dev
```

## Go to the directory
```
cd /home/pi
```

## Download OpenCV
```
wget https://github.com/Itseez/opencv/archive/3.0.0.zip
```

## Unzip archive and go to the directory
```
unzip 3.0.0.zip
cd opencv-3.0.0
```

## Create folder 'release' and go to the directory created
```
mkdir release
cd release
```

## Make and Install OpenCV
```
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D BUILD_NEW_PYTHON_SUPPORT=ON -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON  -D BUILD_EXAMPLES=ON ..
make -j4
sudo make install
```

## Indicate new library
```
sudo ldconfig
```

## Delete unnecessary files
```
rm /home/pi/3.0.0.zip
rm -R /home/pi/opencv-3.0.0
```

## Test your installation
```
cd /home/pi/opencv-3.0.0/samples
```
