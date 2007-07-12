=== Naatan.com MyStats v1.0 ===
Contributors: Naatan
Donate link: http://www.naatan.com/
Tags: statistics, welcome panel
Requires at least: 2.x
Tested up to: 2.1
Stable tag: trunk

Shows some info about the visitor concerning his/her activity on your website.

== Description ==

I have released two versions of this plugin, one that's supporting sessions and one that isn't.
The reason I did this is because some servers don't support the use of sessions, also the script I wrote
creates a new session and this might give errors if other plugins you might be using do the same.
I would advice you to install the plugin that supports sessions, if this gives errors simply install the other one.

The biggest difference is that the plugin with sessions shows you comments/blogs since your last visited date.
The plugin without sessions shows them since your last comment.

== Installation ==

1. Upload the files to your plugins directory
  - naatan_mystats_with-sessions.php *Upload this file if you want to use sessions*
  - naatan_mystats_without-sessions.php *Upload this file if you don't want to use sessions*
2. Enable the plugin in WP Plugin Management
3. Open up your sidebar template (or any other template you want to place it in)
4. Add the following where you want the plugin to appear;

----(Start Copying Below)-----

<?php naatan_mystats(); ?>

----(Stop Copying)-----

5. Save Template
6. Done!

== Arbitrary section ==

When you enable the plugin a little MyStats header will appear at the admin panel options pages.
You can specify two templates, one for when a visitor with previous comments visits and one for new visitors
that do not have a name specified.
If you don't want new visitors to get a MyStats menu simply leave that template empty.
