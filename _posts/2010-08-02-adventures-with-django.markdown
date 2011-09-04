---
author: cbhl
date: '2010-08-02 01:53:49'
layout: post
slug: adventures-with-django
status: publish
title: Adventures with Django
wordpress_id: '171'
categories:
- Thought Dump
---

Touted as "The Web framework for perfectionists with deadlines",
[Django](http://www.djangoproject.com/) is a python-based framework
which provides clean urls, modularity, and a bunch of other things which
should make it easy to create a site that Does The Right Thing. I won't
explain in detail how to start using the framework, because I wouldn't
be able to do the topic justice. The official [Django
documentation](http://docs.djangoproject.com/en/dev/) is actually quite
thorough and easy on the eyes. It's much better-looking than my blog
theme, for sure... I should really get around to replacing it with a
better one. For some crazy reason, I thought that getting a new phone
number would be the perfect time to practice using an MVC-like pattern
in Django. In Django, they use the terms Model, View, and Template...
although [that doesn't really make a great
acronym](http://docs.djangoproject.com/en/dev/faq/general/#django-appears-to-be-a-mvc-framework-but-you-call-the-controller-the-view-and-the-view-the-template-how-come-you-don-t-use-the-standard-names).
In Ruby on Rails, the term MVC, short for Model, View, and Controller,
is quite common. In Microsoft's Silverlight and WPF, the de-facto
analogy is "Model-View-ViewModel", also known as MVVM. Whatever the heck
you call it, the idea is to separate data into a "model", and then have
separate business logic (django: view, rails: controller,
silverlight/wpf: viewmodel) layer and presentation layer (django:
template, rails: view, silverlight/wpf: view)... which isn't exactly a
radical idea. But anyway... so I decided to jump in.
[![image](http://blog.azuresky.ca/blog/wp-content/uploads/2010/08/django-screenshot-150x150.png "django-screenshot")](http://blog.azuresky.ca/blog/wp-content/uploads/2010/08/django-screenshot.png)
The result is this:
[http://m.azuresky.ca/Gee3No](http://m.azuresky.ca/Gee3No) Since I
wasn't familiar with the logic separation required and I was busy with
work, I ended up being a month late and sending out the text messages
late at night. Alas. There's also some mod\_rewrite magic to get the
short URLs, which I should document at some point in the future. On the
plus side, the python DB APIs made it easy to interact with the model --
for example, I used the python API to load the users from my old phone's
contacts backup (in VCARD format on the memory stick) and to set
permissions on what content users could see based on groups. Django also
provides a nice admin interface on top of the model in exchange for a
few minutes of setup, which came in quite handy.
