---
author: cbhl
date: '2011-07-12 11:47:11'
layout: page
slug: gmyk
status: publish
title: GMYK
wordpress_id: '1053'
---

{% highlight python %}
\#!/usr/bin/env python import pygtk
pygtk.require('2.0') import gtk import sys class GladeRunner: def
gtk\_main\_quit(self, object): gtk.main\_quit() return False def
\_\_init\_\_(self): self.builder = gtk.Builder()
self.builder.add\_from\_file(sys.argv[1]) self.window1 =
self.builder.get\_object("window1") self.builder.connect\_signals(self)
self.window1.show() def main(self): gtk.main() print \_\_name\_\_ if
\_\_name\_\_ == "\_\_main\_\_": s = GladeRunner() s.main()
{% endhighlight %}
{% highlight cpp %}
int main(int argc, char \*\*argv) { Gtk::Main kit(argc,
argv); Glib::RefPtr<Gtk::Builder\> refBuilder =
Gtk::Builder::create\_from\_file("straights-gtk.glade");
refBuilder-\>get\_widget("window1", window1); if (window1) {
kit.run(\*window1); } return 0; }
{% endhighlight %}
