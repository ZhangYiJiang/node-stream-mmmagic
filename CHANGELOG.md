# stream-mmmagic changelog

## 2.3.0 (2021/07/03)

  - add typescript types
  - bump deps
  - switch from travis to github actions

## 2.2.0 (2019/10/03)

  - add promise interface
  - drop support for node 4 & 6 (it might still work - but it's no longer tested)
  - added node 12 to test

## 2.1.0 (2018/09/19)

  - support node 10

## 2.0.0 (2017/01/30)
**Major Changes**

  - removed support for setting `require('stream-mmmagic').config.magicFile`
    - `magicFile` option added which can be used during each call instead

**Minor Changes**

  - add `peekBytes` option to control how many bytes of the start of the stream are sent to libmagic
    + default is sufficient for detecting type, but more may improve reliability of getting correct encoding
  - add `magicFile` option which replaces fragile module `config.magicFile` setting
  - add caching of `mmmagic` objects instead of recreating them for every new stream
    + Makes the (safe?) assumption that nobody is using this module with large numbers of unique magic files

## 1.1.0 (2017/01/09)

  - add `splitMime: false` option for #5
  - add tests

## 1.0.0 (2016/08/31)
is backwards compatible with `0.2.0`; bump signifies this is now considered stable after being used 100,000s of times
in a production environment.

  - add support for node 5 & 6

## 0.2.0 (2014/11/12)
**backwards incompatible** using semver; api not stable until 1.0.0

  - function now returns a stream which should be piped from instead of the input stream
  - fix many issues with edge case streams, especially small binary ones

## 0.1.0 (2014/11/06)
*don't use; broken for streams that emit more than 1 chunk*
