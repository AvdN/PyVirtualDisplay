pyvirtualdisplay is a python wrapper for Xvfb_ and Xephyr_


Links:
 * home: https://github.com/ponty/PyVirtualDisplay
 * documentation: http://ponty.github.com/PyVirtualDisplay


Possible applications:
 * GUI testing
 * automatic GUI screenshot

Basic usages
============

Start Xephyr::

    from pyvirtualdisplay import Display
    xephyr=Display(visible=1, size=(320, 240)).start()

Create screenshot of xmessage with Xvfb::

    from easyprocess import EasyProcess
    from pyvirtualdisplay.smartdisplay import SmartDisplay
    with SmartDisplay(visible=0, bgcolor='black') as disp:
        with EasyProcess('xmessage hello'):
            img = disp.waitgrab()
    img.show()

Installation
============

General
--------

 * install Xvfb_ and Xephyr_.
 * install setuptools_
 * optional: pyscreenshot_ and PIL_ should be installed for ``smartdisplay`` submodule
 * install the program::

    # as root
    easy_install pyvirtualdisplay

Ubuntu
----------
::

    sudo apt-get install python-setuptools
    sudo apt-get install xvfb
    sudo apt-get install xserver-xephyr
    sudo easy_install pyvirtualdisplay
    # optional
    sudo apt-get install python-imaging
    sudo apt-get install scrot
    sudo easy_install pyscreenshot


Uninstall
----------

install pip_::

    # as root
    pip uninstall pyvirtualdisplay


.. _setuptools: http://peak.telecommunity.com/DevCenter/EasyInstall
.. _pip: http://pip.openplans.org/
.. _Xvfb: http://en.wikipedia.org/wiki/Xvfb
.. _Xephyr: http://en.wikipedia.org/wiki/Xephyr
.. _pyscreenshot: https://github.com/ponty/pyscreenshot
.. _PIL: http://www.pythonware.com/library/pil/