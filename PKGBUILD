# Script generated with Bloom
pkgdesc="ROS - This package contains a script to generate calibration launch and configurationfiles for your robot. which is based on Michael Ferguson's calibration code"
url='http://ros.org/wiki/calibration_setup_helper'

pkgname='ros-lunar-calibration-setup-helper'
pkgver='0.10.14_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-calibration-launch'
)

conflicts=()
replaces=()

_dir=calibration_setup_helper
source=()
md5sums=()

prepare() {
    cp -R $startdir/calibration_setup_helper $srcdir/calibration_setup_helper
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

