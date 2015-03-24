# jGauge 0.3.0 Alpha 3 - Documentation #

Please note this is an alpha release. Version 0.3.0 is still under development use with caution! ;-)

If you find jGauge useful a link back to the home page <a href='http://www.jgauge.com'>www.jgauge.com</a> or my blog <a href='http://www.dariancabot.com'>www.dariancabot.com</a> is appreciated.

<a href='http://www.jgauge.com/'>See the main project page</a> for more information and downloads.

## Getting Started ##

Include these files in the head of your HTML:
```
<link rel="stylesheet" href="css/gauge_screen.css" type="text/css" />
<!--[if IE]><script type="text/javascript" language="javascript" src="js/excanvas.min.js"></script><![endif]-->
<script language="javascript" type="text/javascript" src="js/jquery-1.4.2.min.js"></script>
<script language="javascript" type="text/javascript" src="js/jQueryRotate.min.js"></script>
<script language="javascript" type="text/javascript" src="js/jgauge-0.3.0.a3.js"></script>
```

In the body of your HTML include a placeholder DIV:

```
<div id="jGaugeDemo" class="jgauge"></div>
```

Use JavaScript to create new jGauge instance and point it to our placeholder DIV.

Then use the jQuery ready() function to initialise the jGauge:

```
<script type="text/javascript">
	var myGauge = new jGauge(); // Create a new jGauge.
	myGauge.id = 'jGaugeDemo'; // Link the new jGauge to the placeholder DIV.

	// This function is called by jQuery once the page has finished loading.
	$(document).ready(function(){
		myGauge.init(); // Put the jGauge on the page by initialising it.
	});
</script> 
```

We're done! Now you can change the gauge value like this (obviously this works well with AJAX):

```
myGauge.setValue(7.35);
```

## Parameters ##

This table lists all the available parameters to customise jGauge.  When a new jGauge is created, the default values are used unless you override them with your own settings.

Please note: **.gaugeId** must be set and unique for each jGauge instance!

| **Parameter** | **Default value** | **Description** |
|:--------------|:------------------|:----------------|
| **.id** | '' _(nothing)_ | The 'id' attribute of the placeholder DIV.<br>Must be set and unique for each jGauge instance. <br>
<tr><td> <b>.segmentStart</b> </td><td> -20 </td><td> Relative to 0&deg; (pointing right / 3-o-clock). </td></tr>
<tr><td> <b>.segmentEnd</b> </td><td> 20 </td><td> Relative to 0&deg; (pointing right / 3-o-clock). </td></tr>
<tr><td> <b>.imagePath</b> </td><td> 'img/jgauge_face_default.png' </td><td> Background image path. </td></tr>
<tr><td> <b>.width</b> </td><td> 160 </td><td> Total width of jGauge. </td></tr>
<tr><td> <b>.height</b> </td><td> 114 </td><td> Total height of jGauge. </td></tr>
<tr><td> <b>.needle.imagePath</b> </td><td> 'img/jgauge_needle_default.png' </td><td> Needle image path. </td></tr>
<tr><td> <b>.needle.limitAction</b> </td><td> limitAction.autoRange </td><td> What to do when the needle hits the limit. </td></tr>
<tr><td> <b>.needle.xOffset</b> </td><td> 0 </td><td> Shift needle position horizontally from center. </td></tr>
<tr><td> <b>.needle.yOffset</b> </td><td> 24 </td><td> Shift needle position vertically from center. </td></tr>
<tr><td> <b>.label.xOffset</b> </td><td> 0 </td><td> Shift value label position horizontally from center. </td></tr>
<tr><td> <b>.label.yOffset</b> </td><td> 20 </td><td> Shift value label position vertically from center. </td></tr>
<tr><td> <b>.label.prefix</b> </td><td> '' <i>(nothing)</i> </td><td> Prefix for the value label (i.e. '$'). </td></tr>
<tr><td> <b>.label.suffix</b> </td><td> '' <i>(nothing)</i> </td><td> Suffic for the value label (i.e. ' kW') </td></tr>
<tr><td> <b>.label.precision</b> </td><td> 1 </td><td> Value label rounding decimal places. </td></tr>
<tr><td> <b>.ticks.count</b> </td><td> 11 </td><td> Number of tick marks around the gauge face. </td></tr>
<tr><td> <b>.ticks.start</b> </td><td> 0 </td><td> Value of the first tick mark. </td></tr>
<tr><td> <b>.ticks.end</b> </td><td> 10 </td><td> Value of the last tick mark. </td></tr>
<tr><td> <b>.ticks.color</b> </td><td> 'rgba(255, 255, 255, 1)' </td><td> Tick mark colour and alpha (opacity). </td></tr>
<tr><td> <b>.ticks.thickness</b> </td><td> 3 </td><td> Tick mark thickness. </td></tr>
<tr><td> <b>.ticks.radius</b> </td><td> 76 </td><td> Tick mark radius (distance from gauge center point). </td></tr>
<tr><td> <b>.ticks.labelPrecision</b> </td><td> 1 </td><td> Rounding decimal places for tick labels. </td></tr>
<tr><td> <b>.ticks.labelRadius</b> </td><td> 65 </td><td> Tick label radius (distance from gauge center point). </td></tr>
<tr><td> <b>.range.radius</b> </td><td> 55 </td><td> Range arc radius (distance from gauge center point). </td></tr>
<tr><td> <b>.range.thickness</b> </td><td> 36 </td><td> Range arc thickness (spread of the arc outwards). </td></tr>
<tr><td> <b>.range.start</b> </td><td> -24 </td><td> Range start point as an angle relative to 0deg (pointing right). </td></tr>
<tr><td> <b>.range.end</b> </td><td> 25 </td><td> Range end point as an angle relative to 0deg (pointing right). </td></tr>
<tr><td> <b>.range.color</b> </td><td> 'rgba(255, 32, 0, 0.2)' </td><td> Colour and alpha (opacity) of the range arc. </td></tr></tbody></table>

<h2>Functions ##

This table lists the functions to use jGauge.  The most important function is **.init()** which must be called on each new jGauge.  Once this is done **.setValue()** can be used to change gauge value (this updates the value label and animates the needle).

| **Function** | **Description** | **Example usage** |
|:-------------|:----------------|:------------------|
| **.init()** | Initializes the gauge and puts it on the page. | `myGauge.init();` |
| **.setValue()** | Sets or updates the gauge value. | `myGauge.setValue(5.2);` |
| **.getValue()** | Gets the current gauge value. | `var myValue = myGauge.getValue();` |
| **.updateTicks()** | Updates the tick marks and tick labels (call after changing tick parameters). | `// Make a change to the ticks.`<br><code>myGauge.tickCount = 6;</code><br><code>// Now we must update ticks.</code><br><code>myGauge.updateTicks();</code> <br>
<tr><td> <b>.updateRange()</b> </td><td> Updates the range (call after changing range parameters). </td><td> <code>// Make a change to the range.</code><br><code>myGauge.rangeStart = -20;</code><br><code>// Now we must update range.</code><br><code>myGauge.updateRange();</code> </td></tr>