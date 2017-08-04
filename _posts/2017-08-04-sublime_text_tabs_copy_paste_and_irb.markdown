---
layout: post
title:  "Sublime Text, Tabs, Copy/Paste and IRB"
date:   2017-08-03 22:28:58 -0400
---


I've noticed some strange behavior copying and pasting code from Sublime Text into irb on Linux over the past couple weeks, and finally figured out what is causing the problem.  Hopefully this post can help anyone else who has been having trouble to resolve the problem.

**The Issue**

Below is a screenshot of the issue I've been having when I try to copy/paste from Sublime Text into irb.  Notice how irb shows "Display all 345 possibilities? (y or n)."  When this happens, irb does not allow you to enter your code and continue testing.

<p><img src="http://imgur.com/a/0smo4.png"></p>

What's happening is that the default formatting of tabs in Sublime Text are causing a problem when they're copy/pasted into irb.  Notice in the screenshot below, with the text highlighted, that the indents before each line of code are displayed as solid lines.  This indicates a tab in Sublime Text, and this is what is causing the issue.

<p><img src="http://imgur.com/a/8hhG2.png"></p>

**The Solution**

Luckily, once I was able to figure out what the problem was, determining the solution was rather simple.  In the above screenshot, you can see at the bottom right of Sublime that it says "Tab Size: 4".  This indicates that tabs are being counted as 4 spaces.  However, they are being formatted as tabs, not as spaces.  If you click where it says "Tab Size: 4", and then click "Indent Using Spaces", you will notice this text changes to "Spaces: 4."  Now, if you type new code in the file and use the tab key, things will look a little different.  Below is an example of code typed after making this change.  Notice what was previously a solid line for the indent is now showing as four dots.

<p><img src="http://imgur.com/a/CCdpe.png"></p>

Unfortunately, just clicking and making this change will not change the default setting in Sublime.  So, unless you want to do this every time you open Sublime, you'll have to make a change directly in Sublime's settings.  To do so, click on "Preferences" and then "Settings" in Sublime.  Then, add the following code to the Preferences.sublime-settings --User file:

```
"translate_tabs_to_spaces": true
```

This will change the default behavior of a tab in Sublime Text to be treated the same as four spaces, and it should solve any issues you were having copy/pasting into irb.

<p><img src="http://imgur.com/a/f9gEB.png"></p>



