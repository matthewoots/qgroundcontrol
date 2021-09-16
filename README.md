# QGroundControl Ground Control Station (Fork Build for Rpi CM4 Ubuntu 20.10)

How to build
```bash
sudo apt install -y qtchooser git qt5-default
git clone https://github.com/qt/qtlocation.git
cd qtlocation
git checkout v5.14.2
git status
cd build/
qmake ../qtlocation.pro 
make -j4
sudo make install
sudo apt-get install -y qtlocation5-dev qtpositioning5-dev qtquickcontrols2-5-dev qml-module-qtquick-controls2 qtquickcontrols2-5-dev qml-module-qtquick-controls2 libqt5svg5* libqt5serialport5* libqt5location5* libqt5charts5* libqt5x11extras5* libqt5waylandclient5* libqt5texttospeech5*
sudo apt-get install -y qml-module-qtquick-layouts qml-module-qtquick-window2 qml-module-qtquick-controls qml-module-qtquick-dialogs
qmake --version # check Qt version make sure it is version 5.14.2 and Qmake is version 3.1
sudo apt-get install -y qtbase5-private-dev qtdeclarative5-private-dev

cd 
git clone https://github.com/matthewoots/qgroundcontrol --branch=Stable_V4.0 --recursive
cd qgroundcontrol/
mkdir build
cd build
qmake -r ../qgroundcontrol.pro CONFIG+=release
make -j3
cd release/
sh qgroundcontrol-start.sh
```

You can reference to https://discuss.ardupilot.org/t/how-to-cross-compile-qgroundcontrol-for-raspberry-pi3/26790/42

[![Releases](https://img.shields.io/github/release/mavlink/QGroundControl.svg)](https://github.com/mavlink/QGroundControl/releases)
[![Travis Build Status](https://travis-ci.org/mavlink/qgroundcontrol.svg?branch=master)](https://travis-ci.org/mavlink/qgroundcontrol)
[![Appveyor Build Status](https://ci.appveyor.com/api/projects/status/crxcm4qayejuvh6c/branch/master?svg=true)](https://ci.appveyor.com/project/mavlink/qgroundcontrol)

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mavlink/qgroundcontrol?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


*QGroundControl* (QGC) is an intuitive and powerful ground control station (GCS) for UAVs.

The primary goal of QGC is ease of use for both first time and professional users. 
It provides full flight control and mission planning for any MAVLink enabled drone, and vehicle setup for both PX4 and ArduPilot powered UAVs. Instructions for *using QGroundControl* are provided in the [User Manual](https://docs.qgroundcontrol.com/en/) (you may not need them because the UI is very intuitive!)

All the code is open-source, so you can contribute and evolve it as you want. 
The [Developer Guide](https://dev.qgroundcontrol.com/en/) explains how to [build](https://dev.qgroundcontrol.com/en/getting_started/) and extend QGC.


Key Links: 
* [Website](http://qgroundcontrol.com) (qgroundcontrol.com)
* [User Manual](https://docs.qgroundcontrol.com/en/)
* [Developer Guide](https://dev.qgroundcontrol.com/en/)
* [Discussion/Support](https://docs.qgroundcontrol.com/en/Support/Support.html)
* [Contributing](https://dev.qgroundcontrol.com/en/contribute/)
* [License](https://github.com/mavlink/qgroundcontrol/blob/master/COPYING.md)
