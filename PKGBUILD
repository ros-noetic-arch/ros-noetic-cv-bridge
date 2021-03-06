# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - This contains CvBridge, which converts between ROS Image messages and OpenCV images."
url='https://wiki.ros.org/cv_bridge'

pkgname='ros-noetic-cv-bridge'
pkgver='1.15.0'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
	ros-noetic-rosconsole
	ros-noetic-sensor-msgs
    ros-noetic-rostest
)

makedepends=(
	cmake
	ros-build-tools
	${ros_makedepends[@]}
	boost
	opencv
	python
    python-numpy
)

ros_depends=(
	ros-noetic-rosconsole
	ros-noetic-sensor-msgs
)

depends=(
	${ros_depends[@]}
	boost
    opencv
	python
)

_dir="vision_opencv-${pkgver}/cv_bridge"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-perception/vision_opencv/archive/${pkgver}.tar.gz")
sha256sums=('dc7faaefeb6dfacbea9479e074a544c9f4df690e0b6910155df8542507b5604c')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
