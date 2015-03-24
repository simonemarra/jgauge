jGauge is a 100% JavaScript dial gauge I created to be a free, lightweight, and powerful alternative to Flash-based gauges.  It can be used on web based dashboards like a speedometer / fuel gauge.


---


## Update - 20110511 ##

**All future development of jGauge is now hosted on GitHub!**

<a href='http://github.com/dariancabot/jGauge'>Check out the early release of version 0.4.0 on GitHub.</a>


---


## jGauge 0.3.0 Alpha 3 released! ##

<a href='http://code.google.com/p/jgauge/downloads/detail?name=jgauge-0.3.0-a3-package.zip'><img src='http://www.dariancabot.com/wp-content/uploads/2010/09/download.png' alt='Download jGauge' /></a> <a href='http://www.dariancabot.com/projects/jgauge_wip/'><img src='http://www.dariancabot.com/wp-content/uploads/2010/09/view.png' alt='View the demonstration' /></a> <a href='http://www.dariancabot.com/projects/jgauge_wip/doc.html'><img src='http://www.dariancabot.com/wp-content/uploads/2010/09/read.png' alt='Read the documentation' /></a>

This is a very early release!  I've only tested it on the most popular and recent browsers.

Compatibility is something I will be addressing after I'm happy with the core functionality.

## Screenshot ##

<img src='http://jgauge.googlecode.com/files/jgauge_0303_screen.jpg' alt='jGauge screenshot' />

## Changelog ##

### Version 0.4.0 - 20110511 ###

  * <a href='http://github.com/dariancabot/jGauge'>Now hosted on GitHub</a>.

### Version 0.3.0 Alpha 3 - 20110303 ###

  * Added automatic 'SI/binary prefix' option for k, M, G, etc...
  * Added SI/binary prefix support for gauge auto-ranging.
  * Added auto-update off CSS from jGauge size settings.
  * Added label and ticks.label color setting.
  * Fixed findUpperLimit bug (not rounding value up).
  * Fixed tick values and needle position when tick.start isn't 0 (zero).
  * Fixed needle z-index issue.
  * jGauge internals are more object oriented.
  * All spelling for functions, vars, etc. changed to American-English from Australian-English. This is to follow the general code standards and avoid confusion.

### Version 0.3.0 Alpha 2 - 20101101 ###

  * Angles now referenced with 0deg to the right (not to the top). This is the more common standard.
  * Defined 'jG' as base state for 'this' making code simpler and improving readability.
  * Fixed canvas element sizing. Now done through DOM, not CSS which never worked. This was only noticeable in gauges larger than 300x150 (the canvas element's default size).
  * All offsets now relative to gauge center point (not upper left corner). This has made positioning elements more intuative for a dial/circle gauge.
  * Finished the .updateRange() function.
  * Created the .resetLayers() function to tidy up after gauge changes that would otherwise bring the modified layer to front causing design problems.
  * Consolidated number precision operations into a new .numberPrecision()function to eliminate code doubling-up.
  * The .findUpperLimit() function has been simplified and now allows for a 'multiple' to be specified to round up to.
  * Various other code tweaks.

## Roadmap ##

jGauge version 0.4.0 is currently being developed and is a complete overhaul of version 0.3.0.  So far there changes made are:

  * jQuery, jQueryRotate, and canvas have been dropped.
  * I'm now using the Raphael JavaScript framework which is much more suitable.
  * There is no longer dependency on the CSS reference making jGauge much more 'self-contained'.
  * Graphics are vector by default.
  * I've shuffled around the internal object relationships to allow for multiple needles and lables.
  * So far all these changes have made jGauge's total file size 30% smaller!
  * Version 0.4.0 also offers greater compatibility and does this without hacky JavaScript exceptions for IE.

Because of these fundamental changes version 0.3.0 Alpha 3 ~~probably~~ _won't_ be developed any further to make way for the much better version 0.4.0.