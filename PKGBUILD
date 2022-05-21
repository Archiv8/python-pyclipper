#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>

_langname="python"
_relname="pyclipper"

pkgname="${_langname}-${_relname}"
pkgver=1.3.0.post2
pkgrel=1
pkgdesc="A cython wrapper for the C++ translation of the Angus Johnson’s Clipper library"
url="https://github.com/fonttools/pyclipper"
arch=(
  "x86_64"
  "i686"
)
license=(
  "MIT"
)
depends=(
  "python"
)
makedepends=(
  "cython"
  "python-setuptools-scm"
)
_tarname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz"
)
sha512sums=(
  "5f383d42c1eeb9c7f54f80540339982467097ddfbf590be8960277fe4da7a25f3b46c8786c8192784bcac3352ec4b26dd034156eba767fafcd8e8daf20d8b3aa"
)

build() {

  cd "${_tarname}"

  python setup.py build
}

package() {

  cd "${_tarname}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname//}" LICENSE
}
