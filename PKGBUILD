# Script generated with Bloom
pkgdesc="ROS - ROS packages for the thormang3_msgs (meta package)"
url='http://wiki.ros.org/thormang3_msgs'

pkgname='ros-kinetic-thormang3-msgs'
pkgver='0.3.0_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-thormang3-action-module-msgs'
'ros-kinetic-thormang3-feet-ft-module-msgs'
'ros-kinetic-thormang3-head-control-module-msgs'
'ros-kinetic-thormang3-manipulation-module-msgs'
'ros-kinetic-thormang3-offset-tuner-msgs'
'ros-kinetic-thormang3-walking-module-msgs'
)

conflicts=()
replaces=()

_dir=thormang3_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/thormang3_msgs $srcdir/thormang3_msgs
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

