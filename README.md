A collection of Pure Data externals using
[pd-lib-builder](https://github.com/pure-data/pd-lib-builder) that
serve as a guide to building your own externals!

## Usage ##

Clone this repo.

Note: The `--recursive` flag is used to bring in the pd-lib-building
git submodule.

    git clone --recursive https://github.com/pelevesque/PureData_C-external-guide.git

## Make ##

To create an external, you start by making it.

To make the helloworld external:

    cd examples/helloworld
    make

## Build ##

Once made, an external must be built.

For this step, you first need a copy of the pure-data source code.

The following build assumes you have cloned the pure-data source code
in a folder side-by-side this repo as to be reacheable by
`../pure-data`.

You can clone the Pure Data source code like so:

    git clone https://github.com/pure-data/pure-data.git

To build the helloworld example, make sure we are already in the
`examples/helloworld` directory of this repo. By default,
pd-lib-builder will attempt to auto-locate an install of Pure Data.
The following command will build the external and install the
distributable files into a subdirectory called
`examples/helloworld/build/helloworld`.

    make install pdincludepath=../../pure-data/src/ objectsdir=./build

See `make help` for more details.

## Distribute ##

If you are using the [deken](https://github.com/pure-data/deken/)
externals packaging tool you can then submit your external to the
[puredata.info repository](http://puredata.info) for other people to
find, like so from inside `examples/helloworld`:

    deken upload ./build/helloworld

You will need to have an account on the site. You probably also want
to have a valid GPG key to sign the package so that users can prove
that it was created by you.

## Thanks ##

This repo is heavily inspired by: https://github.com/pure-data/helloworld
