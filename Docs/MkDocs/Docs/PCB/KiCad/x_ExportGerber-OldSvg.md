# Kicad - Design

**Note this is an older doc I've kept for info** <br>
**If you want an svg export for use with the Laser Cutter see the use of Gerber output and FlatCam to do this instead**

## PCB Design

The first step is to open the PCB Design within KiCad

<a href="../../../images/PCB/KiCad/ExportSvg/Svg1.png"><img src="../../../images/PCB/KiCad/ExportSvg/Svg1.png" height="50%" width="50%" ></a> <br>

### Export Top Layer

Next we're going to export the top layer as an SVG image

  * It's best to avoid the use of the File -> Export Svg option since that doesn't allow for a negative to be created,<br>
    instead we're going to use Plot
  * It's also best to draw a square around the board on the "Edge Cuts" Layer,<br>
    make sure it doesn't come into contact with any of the pins

  * Select **File -> Plot**
  * Select the Front Copper Layer on the left
  * Select the Output directory "svg/"
  * Select Drill marks: **Small**
  * Negative plot: **Ticked**
  * Mirrored Plot: **Unticked** for the front layer
  * Exclude PCB edge layer from other layers: **Unticked** To include the Outer cut line

<a href="../../../images/PCB/KiCad/ExportSvg/Svg2.png"><img src="../../../images/PCB/KiCad/ExportSvg/Svg2.png" height="50%" width="50%" ></a> <br>

Click **Plot** to export the svg

### Export Bottom Layer

Next for the bottom layer repeat as above but make the following changes

  * Select the Bottom Copper Layer on the left, unselect the Front Layer
  * Mirrored Plot: **Ticked** for the bottom layer

<a href="../../../images/PCB/KiCad/ExportSvg/Svg3.png"><img src="../../../images/PCB/KiCad/ExportSvg/Svg3.png" height="50%" width="50%" ></a> <br>

Click **Plot** to export the svg

## Inkscape Edit

Next we need to resize a couple of things within inkscape.

First we want to resize the actual Document

  * Open each svg within inkscape
  * Open up File -> Document Properties
  * Select the white box surrounding the Board
  * Expand the **Resize page to content...**
  * Click **Resize page to drawing or selection** with the white outer box selected

<a href="../../../images/PCB/KiCad/ExportSvg/Svg4.png"><img src="../../../images/PCB/KiCad/ExportSvg/Svg4.png" height="50%" width="50%" ></a> <br>

Next we need to resize the big black box that surrounds the box so that it fits within the document, this is acting as a mask

  * Select the white outline box, and select **Edit -> Copy**
  * Select the Outer black box and Select **Edit -> Paste Size -> Paste Size**
  * At the top Enter X: 0 Y: 0 to position the box at the bottom left corner

<a href="../../../images/PCB/KiCad/ExportSvg/Svg5.png"><img src="../../../images/PCB/KiCad/ExportSvg/Svg5.png" height="50%" width="50%" ></a> <br>

## Examples

Some svg's of adafruit's pcb ruler for testing how small can we go

  * <https://github.com/grbd/CAD.OxBot.Circuit/tree/master/Tests/AdafruitPCBRuller/svg>

A test of the pcb I replicated from the arduino cnc project, I've got no plan on using this (just created it to confirm the wiring is what I thought it was), but maybe a good test

  * [Front Layer](../images/Examples/arduino-cnc-shield-2.02-F.Cu.svg)
  * [Back Layer](../images/Examples/arduino-cnc-shield-2.02-B.Cu.svg)
