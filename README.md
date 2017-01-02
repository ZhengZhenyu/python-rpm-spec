# python-rpm-spec

[![Build Status](https://travis-ci.org/bkircher/python-rpm-spec.svg?branch=master)](https://travis-ci.org/bkircher/python-rpm-spec)

python-rpm-spec is a Python module for parsing RPM spec files.

RPMs are build from a package's sources along with a spec file. The spec file
controls how the RPM is built. This module allows you to parse spec files and
gives you simple access to various bits of information that is contained in the
spec file.

## Examples
```python
from rpm.spec import Spec, replace_macros

spec = Spec.from_file('llvm.spec')
print(spec.version)  # 3.8.0
print(spec.sources[0])  # http://llvm.org/releases/%{version}/%{name}-%{version}.src.tar.xz
print(replace_macros(spec.sources[0], spec)  # http://llvm.org/releases/3.8.0/llvm-3.8.0.src.tar.xz
```

## Dependencies
Except Python 3 no extra dependencies are required.

## Current status
This module does not parse everything of a spec file. Only the pieces I needed.
So there is probably still plenty of stuff missing. However, it should not be
terribly complicated to add support for the missing pieces.

<!-- vim: et sw=4 ts=4:
-->
