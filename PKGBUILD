# Script generated with Bloom
pkgdesc="ROS - Provides a toolchain running through the robot calibration process. This involves capturing calibration data, estimating parameters, and then updating the URDF."
url='http://www.ros.org/wiki/ros_comm'

pkgname='ros-lunar-calibration'
pkgver='0.10.14_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-calibration-estimation'
'ros-lunar-calibration-launch'
'ros-lunar-calibration-msgs'
'ros-lunar-image-cb-detector'
'ros-lunar-interval-intersection'
'ros-lunar-joint-states-settler'
'ros-lunar-laser-cb-detector'
'ros-lunar-monocam-settler'
'ros-lunar-settlerlib'
)

conflicts=()
replaces=()

_dir=calibration
source=()
md5sums=()

prepare() {
    cp -R $startdir/calibration $srcdir/calibration
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

