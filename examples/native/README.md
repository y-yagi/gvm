This example demonstrates a workflow with native code integration.

# Preparation

    gvm install go1.1
    gvm use go1.1
    gvm pkgset create libnative
    gvm pkgset use libnative

# Native Code Installation

    gvm pkgset use libnative
    ./configure --prefix=${GVM_OVERLAY_PREFIX}
    make && make install

# Go Integration Testing

    CGO_CFLAGS="-I${GVM_OVERLAY_PREFIX}/include" CGO_LDFLAGS="${GVM_OVERLAY_PREFIX}/lib/libnative.a" go build -v -x .go build
    ./native
