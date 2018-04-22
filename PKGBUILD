# Script generated with Bloom
pkgdesc="ROS - Tools for calculating the intersection of interval messages coming in on several topics. This package is experimental and unstable. Expect its APIs to change."
url='http://www.ros.org/wiki/interval_intersection'

pkgname='ros-kinetic-interval-intersection'
pkgver='0.10.14_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-calibration-msgs'
'ros-kinetic-catkin>=0.5.68'
'ros-kinetic-geometry-msgs'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-roscpp-serialization'
'ros-kinetic-rostime'
'ros-kinetic-std-msgs'
)

depends=('boost'
'ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-calibration-msgs'
'ros-kinetic-geometry-msgs'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-roscpp-serialization'
'ros-kinetic-rostime'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=interval_intersection
source=()
md5sums=()

prepare() {
    cp -R $startdir/interval_intersection $srcdir/interval_intersection
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

