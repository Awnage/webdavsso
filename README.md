# WebDAVSSO

## About

WebDAVSSO is a [Drupal](https://drupal.org/) 6 module built to facilitate Single Sign On (SSO) for [WebDAV](http://www.webdav.org) clients. It serves as one piece in a Service/Identity provider relationship.

As users log in, the system will store hashed WebDAV compatible passwords. Your WebDAV server can then query this service for their password.

For more information on WebDAV see the [official site](http://www.webdav.org) or [Wikipedia](https://en.wikipedia.org/wiki/WebDAV).

This project was sponsored by [Social & Scientific Systems, Inc.](http://www.s-3.com)

## Installation

### Drupal Module Install

* Place webdavsso folder into sites/all/modules
* Go to Drupal admin interface and install
* Run Drupal's update.php
* You may need to update the module's permissions so that you can access the config
* Click "WebDAV SSO settings" link under the "Administer" menu option
* Add appropriate realms and the server that is serving them
* Log out/in to generate the hashes for yourself

### Service Install

The service installs with the module. The url is 

    https://SERVERNAME/webdavsso/q

The service expects an SSL POST containing only two parameters: u and r, corresponding to the username being queried and the WebDAV realm. On success it will return the user's hashed WebDAV password.

Responses:

    200 OK          : Success, with the content being the hashed WebDAV password
    204 No Content  : No matching active user/realm
    403 Forbidden   : Incorrect formatting of request, with a possible message
    418 I'm a teapot: Multiple hashes, which should not happen

It is up to your server to parse the response and then allow/deny access.

## TODO

* Config flag to toggle SSL for development purposes
* Update the user's login date upon a successful query
* Edit/Deletion of Realms with corresponding deletion of user hashes

## Notes

This module is *not* designed to enable WebDAV access to Drupal nodes or content. For something like that you will want to check out other projects like [WebDAV for Drupal](https://drupal.org/project/webdav).

You should secure the tunnel between your server and this module with appropriate certs

## Authors

**Gregory Wilson**
+ http://drakos7.net
+ http://github.com/awnage
+ http://twitter.com/awnage

## Copyright and license

Copyright 2012 Social & Scientific Systems, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this work except in compliance with the License.
You may obtain a copy of the License in the LICENSE file, or at:

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
