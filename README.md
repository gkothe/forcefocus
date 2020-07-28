@sbspk/forcefocus
=========

> Node module that allows you to steal focus from other windows in Windows.

Microsoft changed the implementation of [SetFocus()](https://msdn.microsoft.com/en-us/library/windows/desktop/ms646312(v=vs.85).aspx) to only allow an app to grant focus to other windows if it currenly holds the focus. If an app that does not have the focus tries to take it, the taskbar will just flash rather than focusing the window. These changes was probably done to improve the user experience, so users would not be disturbed by the focused application suddenly switching.

This module circumvents the restrictions in SetFocus() and allows any window to steal the focus.

It reuses the Electron's built-in `focus()` on other platforms.

Installation
------------

Install `forcefocus` by running:

```sh
$ npm install --save @sbspk/forcefocus
```

Native binaries for Windows, macOS and Linux are built when the module is installed.

Documentation
-------------

**Example**  
```js
const forceFocus = require('forcefocus');
const currentWindow = require('electron').remote.getCurrentWindow();

forceFocus.focusWindow(currentWindow);
```

License
-------

The project is licensed under the Apache 2.0 license.
