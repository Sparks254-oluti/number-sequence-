/*
  Number Sequence Generator for Adobe Illustrator
  -------------------------------------------------
  This script creates a sequence of numbers (1–N)
  either in a vertical list or positioned in a grid.

  Author: ChatGPT
*/

var doc = app.activeDocument;

// === USER SETTINGS ===
var startNumber = 1;         // starting number
var endNumber = 100;         // ending number
var fontSize = 12;           // text size in points
var spacing = 20;            // vertical spacing in points
var xPos = 100;              // X position on artboard
var yPos = 800;              // Starting Y position (top of list)

// === GENERATE NUMBERS ===
for (var i = startNumber; i <= endNumber; i++) {
    var num = doc.textFrames.add();
    num.contents = i.toString();
    num.textRange.characterAttributes.size = fontSize;
    num.left = xPos;
    num.top = yPos - ((i - startNumber) * spacing);
}
alert("✅ Number sequence from " + startNumber + " to " + endNumber + " created!");
