# AstoCAD-Build-Guide

Pasting this command into the linux terminal should download and build AstoCAD from source in Ubuntu 18.0+

Note: source code will be downloaded in the directory from which the command is run.
```
sudo apt install git
  && git clone --recurse-submodules -b AstoCAD-42575 https://github.com/AstroCAD/FreeCAD.git
  && sudo apt install qtbase5-dev qttools5-dev libqt5opengl5-dev libqt5svg5-dev qtwebengine5-dev libqt5xmlpatterns5-dev libqt5x11extras5-dev libpyside2-dev libshiboken2-dev pyside2-tools pyqt5-dev-tools python3-dev python3-matplotlib python3-packaging python3-pivy python3-ply python3-pyside2.qtcore python3-pyside2.qtgui python3-pyside2.qtsvg python3-pyside2.qtwidgets python3-pyside2.qtnetwork python3-pyside2.qtwebengine python3-pyside2.qtwebenginecore python3-pyside2.qtwebenginewidgets python3-pyside2.qtwebchannel libeigen3-dev libgts-bin libgts-dev libkdtree++-dev libmedc-dev libopencv-dev libproj-dev libvtk9-dev libx11-dev libxerces-c-dev libyaml-cpp-dev libzipios++-dev libpcl-dev libcoin-dev libboost-dev libboost-date-time-dev libboost-filesystem-dev libboost-graph-dev libboost-iostreams-dev libboost-program-options-dev libboost-python-dev libboost-regex-dev libboost-serialization-dev libboost-thread-dev python3 swig build-essential cmake libtool lsb-release libocct-data-exchange-dev libocct-draw-dev libocct-foundation-dev libocct-modeling-algorithms-dev libocct-modeling-data-dev libocct-ocaf-dev libocct-visualization-dev occt-draw libspnav-dev checkinstall libsimage-dev pybind11-dev
  && cd ./FreeCAD
  && mkdir build
  && cd build
  && cmake -DCMAKE_BUILD_TYPE=Release ../
  && make -j$(nproc --ignore=2)
  && nautilus --browser ./bin
```
The code will take a long time, possibly hours, to build. At the end of the process, assuming no errors occur, a file browser window will be launched. You should be see two executables, FreeCAD and FreeCADCmd.
