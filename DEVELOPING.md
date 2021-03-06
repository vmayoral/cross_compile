# Developing ros-cross-compile

This document contains instructions, guidelines, and requirements for developing this tool.

## Writing Code

For easiest development, use `virtualenv` to manage the dependency environment.

```
# create a virtualenv
virtualenv venv
# use it
source venv/bin/activate
# install this package in the virtualenv to get dependencies
pip install -e .
# now you can run your work
ros_cross_compile
```

## Tests

These are testing entrypoints:

* Unit tests via `tox`
  * run `tox -e py`
* End-to-end shell script
  * run `./test/run_e2e_test.sh`

## Host Platforms

The target host platforms for this tool are the Tier 1 platforms specified by non-EOL ROS 2 LTS distributions, on x86_64.
Cross-compiling on ARM host platforms is out of scope.

See [REP 2000](https://www.ros.org/reps/rep-2000.html) for this list, which is now:
* Dashing Diademata
  * Ubuntu Bionic 18.04
    * support installation via `pip` and `apt`
  * MacOS Sierra (10.12)
    * support installation via `pip`
  * Windows 10 (VS2019)
    * support installation via `pip`

Though not all of these targets may be fully supported yet, design decisions may not be made that rule out support for those platforms in the future.
