pkgname=niri-column-indicator
pkgver=1.1.1
pkgrel=1
pkgdesc="Column indicator for niri's scrolling layout"
arch=('x86_64' 'aarch64')
url='https://github.com/viacoffee/niri-column-indicator'
license=('GPL-3.0-or-later')
depends=('gcc-libs' 'glibc' 'niri')
makedepends=('rust')
options=('!debug')

# Build the tagged checkout supplied by the release workflow.
prepare() {
    mkdir -p "$srcdir/$pkgname/src"
    cp "$startdir/Cargo.toml" "$startdir/Cargo.lock" "$srcdir/$pkgname/"
    cp "$startdir/src/main.rs" "$srcdir/$pkgname/src/"
}

build() {
    cd "$srcdir/$pkgname"
    cargo build --release --locked
}

check() {
    cd "$srcdir/$pkgname"
    cargo test --locked
}

package() {
    cd "$srcdir/$pkgname"
    install -Dm755 target/release/niri-column-indicator \
        "$pkgdir/usr/bin/niri-column-indicator"
}
