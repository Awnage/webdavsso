# WebDAVSSO

by [Gregory Wilson][http://drakos7.net] and [Rosina Bignall][http://rosinabignall.com]
Sponsored by [Social & Scientific Systems, Inc.][http://www.s-3.com]

## About

WebDAVSSO is a Drupal 6 module built to faciliate Single Sign On (SSO) for WebDAV clients.

As users log in, the system will store hashed WebDAV compatible passwords.

This module is *not* designed to enable WebDAV access to Drupal nodes or content. For something like that you will want to check out other projects like [WebDAV for Drupal][https://drupal.org/project/webdav].


## Installation

Drupal Module Install
* Place webdavsso folder into sites/all/modules
* Go to Drupal admin interface and install
* Run Drupal's update.php
* You may need to update the module's permissions so that you can access the config
* Click "WebDAV SSO settings" link under the "Administer" menu option
* Add appropriate realms and the server that is serving them
* Log out/in to generate the hashes for yourself

Service Install

## TODO

Still need to build the service component