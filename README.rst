============
Django Forum
============

This is a fork of django-forum, originally developed by Ross Poulton. 

This is a very basic forum application that can plug into any
existing Django installation and use it's existing templates,
users, and admin interface. 

It's perfect for adding forum functionality to an existing website.

Original Google Code Page / SVN: http://code.google.com/p/django-forum/
Original authors Home Page: http://www.rossp.org

Current Status
--------------

* It's very basic in terms of features, but it works and is usable.
* Uses Django Admin for maintenance / moderation - no in-line admin.
* Uses existing django Auth and assumes you already have that up and
  running. 
* Uses python-markdown, if present.

Getting Started
---------------

1. Add 'forum' to your INSTALLED_APPS in settings.py.
2. ./manage.py syncdb or ./manage.py migrate
3. Update urls.py: (r'^forum/', include('forum.urls')),
4. Browse to yoursite.com/forum/
5. Enjoy :)

You can include the forum sitemaps in your main sitemap index.
Example:

    from forum.urls import sitemap_dict as forum_sitemap

    yoursitemap_dict.update(forum_sitemap)

    urlpatterns = patterns('',
        (r'^sitemap.xml$', 'django.contrib.sitemaps.views.index', {'sitemaps': yoursitemap_dict}),
        (r'^sitemap-(?P<section>.+)\.xml$', 'django.contrib.sitemaps.views.sitemap', {'sitemaps': yoursitemap_dict}),
    )

Thanks
------

Original creator: Ross Poulton (rossp.org)

The following people have contributed code or ideas to this project. Thank 
you for all of your efforts:

* mandric
* Eric Moritz
* A Alibrahim
* marinho
* canburak
* Erik Wickstrom
* Aron Jones
* Sir Steve H
* xphuture
* bymenda
* macmichael01
