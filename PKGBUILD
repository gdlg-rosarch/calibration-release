# Script generated with Bloom
pkgdesc="ROS - Extracts checkerboard corners from a dense laser snapshot. This package is experimental and unstable. Expect its APIs to change."
url='http://www.ros.org/wiki/laser_cb_detector'

pkgname='ros-lunar-laser-cb-detector'
pkgver='0.10.14_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-actionlib'
'ros-lunar-actionlib-msgs'
'ros-lunar-catkin>=0.5.68'
'ros-lunar-cv-bridge'
'ros-lunar-image-cb-detector'
'ros-lunar-message-filters'
'ros-lunar-roscpp'
'ros-lunar-settlerlib'
'ros-lunar-std-msgs'
)

depends=('ros-lunar-actionlib'
'ros-lunar-actionlib-msgs'
'ros-lunar-cv-bridge'
'ros-lunar-image-cb-detector'
'ros-lunar-message-filters'
'ros-lunar-roscpp'
'ros-lunar-settlerlib'
'ros-lunar-std-msgs'
)

conflicts=()
replaces=()

_dir=laser_cb_detector
source=()
md5sums=()

prepare() {
    cp -R $startdir/laser_cb_detector $srcdir/laser_cb_detector
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

