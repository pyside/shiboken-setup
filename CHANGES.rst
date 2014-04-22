Changes
=======

1.2.1 (2013-08-16)
------------------

Major changes
~~~~~~~~~~~~~

- Better support for more than 9 arguments to methods
- Avoiding a segfault when getting the .name attribute on an enum value with no name

1.2.0 (2013-07-02)
------------------

Major changes
~~~~~~~~~~~~~

- Install the shiboken module to site-packages
- Fix multiple segfaults

Complete list of changes and bug fixes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- Removed old logos from html docs
- Add missing return on module init error
- Don't break -Werror=non-virtual-dtor
- Fixing shiboken test for minimal binding test
- Decref reference to type object
- Fix segfault when using shiboken.delete
- Use non-static method def for instance methods
- Fix bug introduced when recursive_invalidate was added
- fix build in C++11 mode
- Prevent infinite recursion in invalidate
- Fix possible conflict with garbage collector
- Fix possible crash at exit
- Fix handling of unsigned long long and provide unittests
- Add test to illustrate issue on typedef enum
- Use getWrapperForQObject to convert if generating for PySide
- Allow compilation without a python shared library
- Use parent class's metaObject if wrapper is NULL
- Optionally assert on free'd pointer with a valid wrapper
- Find python3 libraries when built with pydebug enabled
- Fix PYSIDE-108 bug and add example
- PYSIDE-83 Fix segfault calling shiboken.dump
- Fix and test case for bug PYSIDE-72
- Override all functions with the same name, not just one
- Update vector conversion
- Add typedef examples to minimal
- Add test files back to cmake
- Don't use it->second after erasing it
- Find function modifications defined in the 2nd+ base class. Fixes bug PYSIDE-54.
- Set a default hash function for all ObjectTypes. Fix bug PYSIDE-42.
- Fix compilation when there is no libxslt installed on the system.
- Fixed resolving of SOABI. SOABI is implemented on Linux, but not on Windows
- Don't use inline methods in dllexported classes to keep VC++ happy
- Use SpooledTemporaryFile in 2.6+ os.tmpfile() fails on win32 if process doesn't have admin permissions
