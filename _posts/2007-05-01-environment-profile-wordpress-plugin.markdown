---
layout: post
title: "Environment Profile WordPress Plugin"
Slug: environment-profile-wordpress-plugin
date: 2007-05-01 06:52:32
tags: [Open Source,Work Life]
---
I'm configuring WordPress to work with an external authentication system and need to automatically log in a user and create a new user in WordPress if none exists. The user's details are available to WordPress in environment variables.

To do this, I'm using three plugins:

- [Angsuman's Authenticated WordPress Plugin](http://blog.taragana.com/index.php/archive/angsumans-authenticated-wordpress-plugin-password-protection-for-your-wordpress-blog/), which forces users to the login page if they're not logged in,
- [Daniel Westermann-Clark's HTTP Authentication WordPress Plugin](http://dev.webadmin.ufl.edu/~dwc/2005/03/10/http-authentication-plugin/), which automatically logs people in if the REMOTE\_USER environment variable is set and creates the user if they don't exist,
- My [Environment Profile WordPress Plugin](http://zaltana.org/documentation/Wordpress_Plugins_Environment_Profile), which automatically updates a user's profile when they are created based on values stored in environment variables.

Firstly, I'd like to thank Daniel for accepting (with changes) my patch to facilitate the creation of non-existent users, an option that can be disabled if you don't want this feature. The first two plugins solved nearly all of my issues, with the exception of using environment variables to fill in the user data on user creation, and in true open source fashion, these three distinct plugins now do a job particularly well, and can be used in conjunction with or separately from each other.

\[Update 6th August\] I've now had approval from the powers that be, and [this plugin is now available](http://zaltana.org/documentation/Wordpress_Plugins_Environment_Profile) for your enjoyment.
