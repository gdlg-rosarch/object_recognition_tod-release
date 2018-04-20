# Script generated with Bloom
pkgdesc="ROS - Textured Object Recognition a standard bag of features approach"
url='http://wg-perception.github.io/tod/'

pkgname='ros-kinetic-object-recognition-tod'
pkgver='0.5.6_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('eigen3'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-ecto'
'ros-kinetic-object-recognition-core'
'ros-kinetic-opencv-candidate'
)

depends=('ros-kinetic-ecto'
'ros-kinetic-ecto-opencv'
'ros-kinetic-ecto-openni'
'ros-kinetic-object-recognition-core'
'ros-kinetic-opencv-candidate'
)

conflicts=()
replaces=()

_dir=object_recognition_tod
source=()
md5sums=()

prepare() {
    cp -R $startdir/object_recognition_tod $srcdir/object_recognition_tod
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

