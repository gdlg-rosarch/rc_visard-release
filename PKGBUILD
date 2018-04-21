# Script generated with Bloom
pkgdesc="ROS - The rc_visard_driver provides data from a Roboception rc_visard 3D sensor on several ROS topics."
url='http://roboception.com/rc_visard'

pkgname='ros-kinetic-rc-visard-driver'
pkgver='2.0.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('curl'
'protobuf'
'ros-kinetic-catkin'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-message-generation'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-rc-dynamics-api>=0.5'
'ros-kinetic-rc-genicam-api'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

depends=('curl'
'protobuf'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-message-runtime'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-rc-dynamics-api>=0.5'
'ros-kinetic-rc-genicam-api'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=rc_visard_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/rc_visard_driver $srcdir/rc_visard_driver
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

