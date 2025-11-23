# OWASP CRS - Traffic Oberservation Plugin

This is an offical CRS plugin that logs information about requests that is not normally logged.

We are planning to do performance testing. But that depends on real world sample traffic. Now the problem is
there is relatively little litterature on representative HTTP traffic.

More information about this idea: https://github.com/coreruleset/coreruleset/wiki/Dev-Retreat-2025-Sample-Traffic

This plugin writes down this information with the idea to bring up this information.

As is, the plugin writes a single log message (non-blocking alert) per request.

Information we are interested in:

* HTTP protocol version
* HTTP Method
* URI
* Query string parameters
* Request body
* Request body content type: urlencoded, XML, JSON
* HTTP request headers, special handling of User-Agent and Referer
* HTTP request cookies
* HTTP response status code
* HTTP response headers
* HTTP response body
* HTTP response body content type
* Session characteristics (number, order and rhythm of requests, etc. - we're probably ignoring this)
* HTTP/2 and 3 specific characteristics like number of streams and the like, but that is not accessible for ModSec right now

## Installation

Put the contents of the `plugin` folder into your installation's CRS4 `plugin` folder. The plugin is active by default.

## License

Copyright (c) 2021-2025 OWASP CRS project. All rights reserved.

The OWASP CRS and its official plugins are
distributed under Apache Software License (ASL) version 2.
Please see the enclosed LICENSE file for full details.
