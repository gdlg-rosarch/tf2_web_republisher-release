# Script generated with Bloom
pkgdesc="ROS - Republishing of Selected TFs"
url='http://ros.org/wiki/tf2_web_republisher'

pkgname='ros-kinetic-tf2-web-republisher'
pkgver='0.3.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-tf'
'ros-kinetic-tf2-ros'
)

depends=('ros-kinetic-actionlib'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-tf2-ros'
)

conflicts=()
replaces=()

_dir=tf2_web_republisher
source=()
md5sums=()

prepare() {
    cp -R $startdir/tf2_web_republisher $srcdir/tf2_web_republisher
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

