# Script generated with Bloom
pkgdesc="ROS - The rc_visard_driver provides data from a Roboception rc_visard 3D sensor on several ROS topics."
url='http://roboception.com/rc_visard'

pkgname='ros-lunar-rc-visard-driver'
pkgver='2.0.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('curl'
'protobuf'
'ros-lunar-catkin'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-geometry-msgs'
'ros-lunar-image-transport'
'ros-lunar-message-generation'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-rc-dynamics-api>=0.5'
'ros-lunar-rc-genicam-api'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-srvs'
'ros-lunar-stereo-msgs'
'ros-lunar-tf'
'ros-lunar-visualization-msgs'
)

depends=('curl'
'protobuf'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-geometry-msgs'
'ros-lunar-image-transport'
'ros-lunar-message-runtime'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-rc-dynamics-api>=0.5'
'ros-lunar-rc-genicam-api'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-srvs'
'ros-lunar-stereo-msgs'
'ros-lunar-tf'
'ros-lunar-visualization-msgs'
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

