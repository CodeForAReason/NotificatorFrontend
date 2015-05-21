Notificator Frontend
====================

Mobile and web application for Notificator

Setup
-----

* install nodejs and npm

run (with sudo if linux or macosx)::

    npm install -g yo grunt-cli bower cordova
    npm install
    bower install
    grunt server

visit http://127.0.0.1:9000

to build android app install android sdk, on linux::

    wget http://dl.google.com/android/android-sdk_r24.0.2-linux.tgz
    tar -xzf android-sdk_r24.0.2-linux.tgz

    echo "export PATH=\$PATH:\$HOME/android-sdk-linux/tools:\$HOME/android-sdk-linux/platform-tools:\$HOME/android-sdk-linux/build-tools/19.1.0" >> $HOME/.bashrc
    bash

    android update sdk -a --no-ui --filter "platform-tools"
    android update sdk -a --no-ui --filter "android-19"
    android update sdk -a --no-ui --filter "sys-img-armeabi-v7a-android-19"
    android update sdk -a --no-ui --filter "build-tools-19.1.0"
    android create avd --name myandroid -t "android-19"

    mkdir phonegap
    cd phonegap
    cordova create .
    cordova platform add android
    rm config.xml
    cd ..
    grunt platform-build
    cd phonegap
    cordova run --device android

for the last step you need to have your android device connected via usb and
development mode enabled.
