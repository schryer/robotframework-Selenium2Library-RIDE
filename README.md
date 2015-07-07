# Example: robotframework + Selenium2Library + RIDE

This repository provides a simple test suite that
checks the login and logout capabilities of the
python.org website using robotframework together
with Selenium2Library and the RIDE editor.

## Install the base robotframework tool:

```
mkvirtualenv test
pip install robotframework
pip install robotframework-selenium2library
```

The [Main test file](./example_testsuite.txt) can now be executed directly:

```
pybot example_testsuite.txt
```

## Install the [RIDE](https://github.com/robotframework/RIDE/wiki) editor:

sudo apt-get install python-wxgtk2.8
sudo apt-get install python-wxversion

pip install robotframework-ride 

The [Main test file](./example_testsuite.txt) can now be edited in
[RIDE](https://github.com/robotframework/RIDE/wiki):

```
ride.py example_testsuite.txt
```

Additional
[keywords and variables](./example_testsuite_resource_file.txt) have
been defined to improve both the readability and maintainability of
these tests.



