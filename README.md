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
    $ repo init -u git@github.com:orbital-systems/dey-manifest.git -b master
    $ repo sync -j8 --no-repo-verify
    ```

4. Setup build environment
   This is the default way of setting up the build environment. It requires that all the tools needed
   for building are installed locally on your machine.

   ```
   $ source setup.sh
   ```

   The alternate way does not require this. Instead, if you do not already have it, install docker. Then
   run the script

   ```
   $ ./start_docker.sh
   ```

   The script will create the docker image, start it and throw you into a bash shell inside it. It
   will even tell you how to build the project. The environment is already correctly setup.

   If you would like to use this method from vs code, it is possible. It requires some additional setup.
   One way to do it is to start the docker environment like above and then use
   `Dev Containers: Attach to Running Container`. Then you have to set up a build script yourself, which
   sources the `setup.sh` script and runs `bitbake` to build your image.

5. Build the swu upgrade image
   ```
   $ bitbake orbital-image-swu orbital-image-desktop-swu
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
