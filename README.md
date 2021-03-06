# EspecWebDoc
Issue Tracker &amp; documentation for Espec Universal Web Controller.

## Version History
Current Version: 2.2.1

Updates currently must be distrubuted via the [espec service department](http://www.espec.com/na/support/).

### 2.2.1
  * Fix static file versioning so that updated static files do not require manual refresh (issue #47).
  * Fix Network view incorrect color for off chambers (issue #46)
  * Fix issue loading in neighboring chambers when not logged in (issue #45)

### 2.2.0
  * Link to other controllers on network in the breadcrumb bar (web controller name is now a drop down)
  * Add a new view for screens wider that 1600 pixels
  * Add current program cycles/counter status to the api (v1.1)
  * Multi-thread database update process for chambers with multiple controllers (makes interface more responsive)
  * Clicking the monitor tab's graph now results in a easier to read pop up in place of a list below the graph.
  * Add the network view giving an at a glance view of all chambers on the network.
  * Proxy support for sending emails (required if the target network requires all traffic to go through a proxy to reach the internet).
  * Watlow F4 Support.
  * Additional controls for the monitor tab's graph (independent axis zooming, zoom extents, disable scrool wheel controls).
    * A future update will make these settings persistant per user.
  * Reconfigure apache for better response times under heavier load.
  * [Online core](http://www.espec.co.jp/english/products/env-test/pcs/) is now fully supported.
  * Bug Fixes:
    * WatlowF4T cascade loop setpoint minumum now works corretly instead of always returning -100
    * Firefox no longer triggers "server offline" on form submission.
    * Wizard modals no longer overflow off te screen on IE (all modals now scroll internally instead of making the page longer)
    * Configurating EN chamber using the presets now works.
    * /api/v1.0/chambers/1/events/1 now works (accessing event by id does not work).
    * Database connection errors no longer occur on first boot.
    * Firmware update process fixed for future updates (currently returns error instead of success message).
    * Navigating directly to program editor when not logged in now returns decent error response instead of error page.
    * Trying to delete a running program on the WatlowF4T now returns error message instead of false success messsage.
    * Monitor tab's graph legend is now clickable when the page initially loads (was not clickable until graph refreshed).
    * Submitting a form with an expired CSRF token now explains why the form submission failed instead of going to a useless error page.
    * javascript files used by the web ui are now versioned so that hard page refreshes are not required after updates.

### 2.1.2
  * Bug fixes for multi controller chambers.

### 2.1.1:
  * Add better descriptions of chamber config options.
  * Add icons for loop names (defaults to none)

### 2.1.0:
  * Merge multiple page system into a single page approach.
  * Add support for for cascade on the WatlowF4T
  * Add support for the Espec P300 chamber controller.
  * Add support for the Espec SCP-220 chamber controller.
  * Add TCP direct interface to chamber controller.
    * Port 502 for modbus based chamber controllrs (WatlowF4T)
    * Port 10001 for Espec P300/SCP-220
  * Add REST API.
  * Add message when server is offline.
  * Add new first configuration wizard.
  * Notify user of non working browsers (ie8 and older)
  * Switch to MySQL backend, (this makes updating from 2.0.0 difficult.
  * Move background error messages to setup screen to stop spamming user with non critical errors.
  * Add support for multi-controller chambers ie large IR chambers.

### 2.0.0:
  * Initial Redesign, WatlowF4T support only.
  
### 1.1.4:
  * Make baud rate configurable, SCP has intermittent issues with 19200, P300 requires 19200 for internal installations.
  * Add basic install instructions to config.html, auto-detect now figures out baud rate.
  * Correct TCP forwarder to properly handle client disconnects/timeouts.
  
### 1.1.3:
  * Correct issue where programs could not be saved when TCPForwarding is disabled.
  
### 1.1.2:
  * Correct program reads incorrectly showing humidity active and ignoring granity.
  
### 1.1.1:
  * Change serial device to /dev/ttyUSB0 (default + all preset files).
  * Correct program downloads. cgi data now always array with new ruby version.
  
### 1.1.0:
  * Merge SCP220 firmware into P300 firmwares.
  * Correct data logging process to use configured settings not autodetection (autodetection randomly incorrect).
  * Change baud rate to 19200.
  * Change maximum # of data points too 1000000 (can be changed for use on old gumstix hardware).
  * Speed up CSV generation and graph data collection algorithm.
  * Add auto configure button for everything except humdity graph (cannot be auto detected).
  * Remove Time signal configuration options, in the future will be replaced with usefull individual selection system.
  * Update ruby backend for newer 1.9.X versions
  * Add current list of custom humidity graphs.
  * Support new Hardware (raspberry pi) much faster and allows for more data storage.
  * Add ability to display MAC address, passcode protected.
  * Add basic status menu on video outputs and ssh login.
  
### 1.0.0 (old hardware only):
  * Initial P300 Release
