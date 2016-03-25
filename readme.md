Codecov Fortran Example
=======================

| [https://codecov.io][1] | [@codecov][2] | [hello@codecov.io][3] |
| ----------------------- | ------------- | --------------------- |

This repository serves as an **example** on how to use [Codecov Global][4] for Fortran.

## Usage

Fortran outpus `gcov` reports for all your files covered. To create
these files all you need to do is to add the `-fprofile-arcs -ftest-coverage` flags to `gfortran` when building.

```
gfortran -fprofile-arcs -ftest-coverage -O0 hello.f90 -o hello
./hello
```

For a slightly more complicated version check out the
[json-fortran](https://github.com/jacobwilliams/json-fortran) project.

# Travis CI

Add to your `.travis.yml` file.
```yml
after_success:
  - bash <(curl -s https://codecov.io/bash)
```

## Private Repos

Add to your `.travis.yml` file.
```yml
after_success:
  - bash <(curl -s https://codecov.io/bash) -t uuid-repo-token
```

View source and learn more about [Codecov Global Uploader][4]

[1]: https://codecov.io/
[2]: https://twitter.com/codecov
[3]: mailto:hello@codecov.io
[4]: https://github.com/codecov/codecov-bash
