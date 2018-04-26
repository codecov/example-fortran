# [Codecov][1] Fortran Example
## Guide
### Travis Setup

Add to your `.travis.yml` file.
```yml
language: c

after_success:
 - bash <(curl -s https://codecov.io/bash)
```
### Produce Coverage Reports

Fortran outpus `gcov` reports for all your files covered. To create
these files all you need to do is to add the `-fprofile-arcs -ftest-coverage` flags to `gfortran` when building.

```
gfortran -fprofile-arcs -ftest-coverage -O0 hello.f90 -o hello
./hello
```

For a slightly more complicated version check out the
[json-fortran](https://github.com/jacobwilliams/json-fortran) project.

## Caveats
### Private Repos
Add to your `.travis.yml` file.
```yml
after_success:
  - bash <(curl -s https://codecov.io/bash) -t uuid-repo-token
```

1. More documentation at https://docs.codecov.io
2. Configure codecov through the `codecov.yml`  https://docs.codecov.io/docs/codecov-yaml

We are happy to help if you have any questions. Please contact email our Support at [support@codecov.io](mailto:support@codecov.io)

[1]: https://codecov.io/
[4]: https://github.com/codecov/codecov-python
