# py_repro

Execute:
```sh
bazel run //app # works as expected
bazel run @pip3//luigi:bin-luigi # can not import module luigi for some reason
```

To simplify the case one can also execute:
```sh
echo "__requires__ = 'luigi==2.8.5'
import re
import sys

from luigi import cmdline

if __name__ == '__main__':
    cmdline.luigi_run()
" > $(bazel info output_base)/external/pip3/luigi/bin/luigi.py
bazel run @pip3//luigi:bin-luigi # same error/issue as before
```