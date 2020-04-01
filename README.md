Digi Embedded Yocto (DEY) manifest
==================================

This repository contains the manifest files for the Digi Embedded Yocto
distribution modified for use by Orbital Systems.

Installing Digi Embedded Yocto
------------------------------

To download Digi Embedded Yocto, you need the repo tool.

Follow these steps to install Digi Embedded Yocto:

1. Download repo to a directory within your path and add execution permissions.

    ```
    $ sudo curl -o /usr/local/bin/repo http://commondatastorage.googleapis.com/git-repo-downloads/repo
    $ sudo chmod a+x /usr/local/bin/repo
    ```

2. Create an installation folder with user write permissions; for example,
    `~/src/dey` and navigate to that folder.

    ```
    $ mkdir ~/src/dey
    $ cd ~/src/dey
    ```

3. Use repo to download Digi Embedded Yocto.

    ```
    $ repo init -u https://github.com/orbital-systems/dey-manifest.git -b orbital
    $ repo sync -j8 --no-repo-verify
    ```

4. Setup build environment
   ```
   $ source setup.sh
   ```

License
-------
Copyright 2018, Digi International Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
