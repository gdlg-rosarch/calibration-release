# Script generated with Bloom
pkgdesc="ROS - Listens on a ImageFeatures topic, and waits for the data to settle. This package is experimental and unstable. Expect its APIs to change."
url='http://www.ros.org/wiki/monocam_settler'

pkgname='ros-kinetic-monocam-settler'
pkgver='0.10.14_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin>=0.5.68'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp-serialization'
'ros-kinetic-settlerlib'
'ros-kinetic-std-msgs'
)

depends=('ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp-serialization'
'ros-kinetic-settlerlib'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=monocam_settler
source=()
md5sums=()

prepare() {
    cp -R $startdir/monocam_settler $srcdir/monocam_settler
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

