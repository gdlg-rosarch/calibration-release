# Script generated with Bloom
pkgdesc="ROS - Provides a node that reports how long a subset of joints has been settled. That is, it calculates how long a set of joints has remained within a specified threshold. This package is experimental and unstable. Expect its APIs to change."
url='http://www.ros.org/wiki/joint_states_settler'

pkgname='ros-lunar-joint-states-settler'
pkgver='0.10.14_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-actionlib'
'ros-lunar-actionlib-msgs'
'ros-lunar-catkin>=0.5.68'
'ros-lunar-rosconsole'
'ros-lunar-roscpp'
'ros-lunar-roscpp-serialization'
'ros-lunar-settlerlib'
'ros-lunar-std-msgs'
)

depends=('ros-lunar-actionlib'
'ros-lunar-actionlib-msgs'
'ros-lunar-rosconsole'
'ros-lunar-roscpp'
'ros-lunar-roscpp-serialization'
'ros-lunar-settlerlib'
'ros-lunar-std-msgs'
)

conflicts=()
replaces=()

_dir=joint_states_settler
source=()
md5sums=()

prepare() {
    cp -R $startdir/joint_states_settler $srcdir/joint_states_settler
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

