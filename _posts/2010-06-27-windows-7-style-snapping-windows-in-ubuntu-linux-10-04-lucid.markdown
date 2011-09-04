---
author: cbhl
date: '2010-06-27 13:58:54'
layout: post
slug: windows-7-style-snapping-windows-in-ubuntu-linux-10-04-lucid
status: publish
title: Windows 7-style Snapping Windows in Ubuntu Linux 10.04 (Lucid)
wordpress_id: '101'
categories:
- Programming
---

Having spent too many long hours at work with a Windows 7 machine, it's
really awkward going back to Ubuntu and not having windows snap to the
edges when I drag windows to the edge of the screen. Luckily, it's
rather easy to customize Compiz (the default window manager for Ubuntu)
so that it acts in this way. Most of these instructions can already be
found on Google, but I'm compiling them here for future reference.
Windows 7 only allows three main types of snapping -- left half, right
half, and full screen by dragging the window to the left, right, and top
of the screen respectively, although the grid plugin I'm using below
lets you dock windows in all the obvious places so feel free to adjust
the procedure as you see fit. These instructions have only been tested
on a single-monitor setup, but then again, even Windows 7 acts funny
when you try to use Aero Snap (or whatever it's called) on a dual-head
setup. (If the monitors are side-by-side, snapping to the top snaps full
screen to the current monitor. You can only snap to the left-most edge
of the left-most monitor, and likewise for the right-most monitor. I
haven't tested Aero Snap for two monitors that are arranged vertically;
and don't intend on doing so in the near future.) **Before You Begin**
You will need to install the following packages if they're not already
installed:
-   compizconfig-settings-manager
-   compiz-fusion-plugins-extra
-   xautomation

Most of this software isn't "officially supported" by Canonical, but
that shouldn't stop you from using it in most cases. You may need to
[add additional
repositories](https://help.ubuntu.com/community/Repositories/Ubuntu) in
order to install the packages. For the lazy, you can just enter the
following command into a terminal. (Note: If you don't understand what
the following command does, it is highly recommended that you use
Synaptic Package Manager to install the software yourself instead.)

{% highlight bash %}
sudo aptitude install compizconfig-settings-manager
compiz-fusion-plugins-extra xautomation
{% endhighlight %}
 **Open the CompizConfig
Settings Manager**
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-300x110.png "Click System | Preferences | CompizConfig Settings Manager")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot.png)
Click System | Preferences | CompizConfig Settings Manager. If you can't
find this menu item, make sure that you installed the
compizconfig-settings-manager package. **Enable the Grid Plugin**
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-2-300x191.png "Click the Window Management category")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-2.png)
Click the Window Management category.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-4-300x55.png "Select Grid")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-4.png)
Select Grid. If Grid does not appear, make sure you installed the
compiz-fusion-plugins-extra package.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-5-300x186.png "Note default key shortcuts (e.g Ctrl+Alt+KP6)")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-5.png)
Note the default key shortcuts. The key shortcuts use Ctrl and Alt, as
well as the keypad numeric keys (not to be confused with the number keys
above the letters on your keyboard). So KP6 corresponds to the 6 key on
the keypad. If you change these, you will need to update the parameters
given to xte, below.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-6.png "Enable the Grid Plugin")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-6.png)
Enable the Grid Plugin. **Create Edge Bindings**
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-71-300x59.png "Click the All category")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-71.png)
Click the All category.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-8-300x76.png "Click Commands")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-8.png)
Click Commands
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-11-300x147.png "Here we will create commands using the xte program that will trigger the keyboard shortcuts for the Grid plugin")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-11.png)
Here we will create commands using the xte program that will trigger the
keyboard shortcuts for the Grid plugin. 
{% highlight bash %}
xte 'keydown Control\_L'
'keydown Alt\_L' 'key KP\_4' 'keyup Control\_L' 'keyup Alt\_L' xte
'keydown Alt\_L' 'key F10' 'keyup Alt\_L' xte 'keydown Control\_L'
'keydown Alt\_L' 'key KP\_6' 'keyup Control\_L' 'keyup Alt\_L'
{% endhighlight %}

[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-12c-300x175.png "After Entering the Commands")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-12c.png)
After entering the commands, the screen should look like this.
**Update:** Setting command 1 (the top edge binding) to read ALT-F10
(instead of Ctrl-Alt-KP\_5 as per the screen shot) will cause the
current window to be "properly" maximized. Using the old method will
allow you to toggle maximizing by moving the mouse to the top edge,
which may be confusing.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-13-300x170.png "Click the Edge bindings tab")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-13.png)
Click the Edge bindings tab. To set the bindings for the commands we
created earlier (click the button that says None).
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-15.png "Select the edge in this window")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-15.png)
Select the edge in this window.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-16-300x85.png "If you get this pop-up, disable the other binding")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-16.png)
If you get this pop-up, disable the other binding.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-21.png "Finished edge bindings")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-21.png)
Here are the finished edge bindings. **Adjust Edge Trigger Delay** If
you use it now, just touching the edge will cause the window to change
size, which is annoying. So we set an edge trigger delay.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-22-300x58.png "Click General Options")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-22.png)
Click General Options
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-23-300x233.png "General Options")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-23.png)
General Options
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-24.png "Adjust the edge trigger delay")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-24.png)
Adjust the edge trigger delay by using the mouse or entering a value. A
value of 400-500 ms is reasonable, but feel free to adjust it. **Final
Thoughts**
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-25.png "Voila")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/06/Screenshot-25.png)
Voila! The finished product. Of course, this "emulation" isn't perfect:
-   You won't get the huge blue silhouette of the window's new position.
-   The binding will trigger regardless of whether you are dragging a
    window or whether you just leave the mouse cursor at the edge of the
    screen
-   If a window has a minimum size, when the window is resized by the
    grid plugin, it may take up more than half the screen.

But it does the job, for someone who's used to gestures introduced in
Windows 7 and can't be bothered to resize windows manually any more.
