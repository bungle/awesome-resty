# awesome-resty

A List of OpenResty / Nginx modules, Lua libraries, and related resources.

## What is OpenResty

![OpenResty Logo](https://github.com/bungle/awesome-resty/raw/master/images/logo.png)

OpenResty is a full-fledged web platform by integrating the standard Nginx core, LuaJIT, many carefully written Lua libraries, lots of high quality 3rd-party Nginx modules, and most of their external dependencies. It is designed to help developers easily build scalable web applications, web services, and dynamic web gateways.

By taking advantage of various well-designed Nginx modules (most of which are developed by the OpenResty team themselves), OpenResty effectively turns the nginx server into a powerful web app server, in which the web developers can use the Lua programming language to script various existing nginx C modules and Lua modules and construct extremely high-performance web applications that are capable to handle 10K ~ 1000K+ connections in a single box.

OpenResty aims to run your server-side web app completely in the Nginx server, leveraging Nginx's event model to do non-blocking I/O not only with the HTTP clients, but also with remote backends like MySQL, PostgreSQL, Memcached, and Redis.

Real-world applications of OpenResty range from dynamic web portals and web gateways, web application firewalls, web service platforms for mobile apps/advertising/distributed storage/data analytics, to full-fledged dynamic web applications and web sites. The hardware used to run OpenResty also ranges from very big metals to embedded devices with very limited resources. It is not uncommon for our production users to serve billions of requests daily for millions of active users with just a handful of machines.

OpenResty is not an Nginx fork. It is just a software bundle. Most of the patches applied to the Nginx core in OpenResty have already been submitted to the official Nginx team and most of the patches submitted have also been accepted. We are trying hard not to fork Nginx and always to use the latest best Nginx core from the official Nginx team.

## Official Channels

* Web Site: http://openresty.org/
* Mailing List: https://groups.google.com/forum/#!forum/openresty-en ([Chinese List](https://groups.google.com/forum/#!forum/openresty))
* Github Organization: https://github.com/openresty
* Lead Developer: [@agentzh](https://github.com/agentzh)
* OpenResty Package Manager (`opm`): [package repository](https://opm.openresty.org/), [opm sources](https://github.com/openresty/opm)

## How to Contribute on this List?

There are at least three different ways to contribute:

1. [Create a New Issue](https://github.com/bungle/awesome-resty/issues/new) where you describe the needed additions, deletions or changes.
2. [Fork this repository](https://github.com/bungle/awesome-resty/fork) and make the changes, and create a pull request.
3. [Post a reply](https://groups.google.com/forum/#!topic/openresty-en/VSj4_8GNORI) in the awesome-resty thread in openresty-en mailing list.

## Contents

* [Modules](#modules)
  * [Core Modules](#core-modules)
  * [Core Nginx Modules](#core-nginx-modules)
  * [Third-party Nginx Modules](#third-party-nginx-modules)
* [Libraries](#libraries)
  * [Core Libraries](#core-libraries)
  * [Web Frameworks](#web-frameworks)
  * [Web Development Essentials](#web-development-essentials)
  * [Routing Libraries](#routing-libraries)
  * [Request Argments Parsers](#request-argments-parsers)
  * [Middleware and API Tools](#middleware-and-api-tools)
  * [Templating](#templating)
  * [Validation](#validation)
  * [Authentication and Authorization](#authentication-and-authorization)
  * [Cryptography](#cryptography)
  * [Networking](#networking)
  * [Databases and Storages](#databases-and-storages)
  * [Testing and Profiling](#testing-and-profiling)
  * [Message Queuing and Task Management](#message-queuing-and-task-management)
  * [Bar Codes and QR Codes](#bar-codes-and-qr-codes)
  * [Utilities](#utilities)
  * [Date and Time](#date-and-time)
  * [Compression](#compression)
  * [Text Formats](#text-formats)
  * [Binary Formats](#binary-formats)
  * [Document Formats](#document-formats)
  * [Image Formats](#image-formats)
  * [Localization](#localization)
  * [Caching](#caching)
  * [Metrics and Statistics](#metrics-and-statistics)
  * [Logging](#logging)
  * [Functional Programming](#functional-programming)
  * [Web APIs](#web-apis)
  * [Other Sources for Libraries](#other-sources-for-libraries)
* [Books and Tutorials](#books-and-tutorials)
  * [Books](#books)
  * [Tutorials and Guides](#tutorials-and-guides)
* [Videos](#videos)
* [Conferences, Workshops and Events](#conferences-workshops-and-events)
* [Demo Applications](#demo-applications)
* [See Also](#see-also)
* [License](#license)

## Modules

#### Core Modules

Core modules come bundled in OpenResty package.

* [ngx_openresty](https://github.com/openresty/openresty) — Turning Nginx into a full-fledged Web App Server - Sources for OpenResty Bundle Generation
* [lua-nginx-module](https://github.com/openresty/lua-nginx-module) — Embed the power of Lua into Nginx
* [stream-lua-nginx-module](https://github.com/openresty/stream-lua-nginx-module) — Embed the power of Lua into Nginx stream/TCP Servers
* [echo-nginx-module](https://github.com/openresty/echo-nginx-module) — An Nginx module for bringing the power of "echo", "sleep", "time" and more to Nginx's config file
* [xss-nginx-module](https://github.com/openresty/xss-nginx-module) — Native support for cross-site scripting (XSS) in an nginx
* [set-misc-nginx-module](https://github.com/openresty/set-misc-nginx-module) — Various set_xxx directives added to nginx's rewrite module (md5/sha1, sql/json quoting, and many more)
* [encrypted-session-nginx-module](https://github.com/openresty/encrypted-session-nginx-module) — Encrypt and decrypt Nginx variable values
* [srcache-nginx-module](https://github.com/openresty/srcache-nginx-module) — Transparent subrequest-based caching layout for arbitrary nginx locations
* [lua-upstream-nginx-module](https://github.com/openresty/lua-upstream-nginx-module) — Nginx C module to expose Lua API to ngx_lua for Nginx upstreams
* [headers-more-nginx-module](https://github.com/openresty/headers-more-nginx-module) — Set and clear input and output headers...more than "add"!
* [array-var-nginx-module](https://github.com/openresty/array-var-nginx-module) — Add support for array variables to nginx config files
* [memc-nginx-module](https://github.com/openresty/memc-nginx-module) — An extended version of the standard memcached module that supports set, add, delete, and many more memcached commands
* [redis2-nginx-module](https://github.com/openresty/redis2-nginx-module) — Nginx upstream module for the Redis 2.0 protocol
* [rds-json-nginx-module](https://github.com/openresty/rds-json-nginx-module) — An nginx output filter that formats Resty DBD Streams generated by ngx_drizzle and others to JSON
* [rds-csv-nginx-module](https://github.com/openresty/rds-csv-nginx-module) — Nginx output filter module to convert Resty-DBD-Streams (RDS) to Comma-Separated Values (CSV)
* [drizzle-nginx-module](https://github.com/openresty/drizzle-nginx-module) — An Nginx upstream module that talks to mysql and drizzle by libdrizzle
* [ngx_postgres](https://github.com/FRiCKLE/ngx_postgres) — Upstream module that allows Nginx to communicate directly with PostgreSQL database
* [form-input-nginx-module](https://github.com/calio/form-input-nginx-module) — This is a nginx module that reads HTTP POST and PUT request body encoded in "application/x-www-form-urlencoded", and parse the arguments in request body into nginx variables.
* [ngx_coolkit](https://github.com/FRiCKLE/ngx_coolkit) — Collection of small and useful nginx add-ons
* [ngx_devel_kit](https://github.com/simpl/ngx_devel_kit) — an Nginx module that adds additional generic tools that module developers can use in their own modules

Please also note that there is **`resty`** command line client included in OpenResty bundle. The [command line client sources](https://github.com/openresty/resty-cli) can be found on Github.

#### Core Nginx Modules

To learn more about Nginx Core Modules, please refer [Nginx Documentation](http://nginx.org/en/docs/). Some modules that come with Nginx are (not all of them are build by default):

* [ngx_http_core_module](http://nginx.org/en/docs/http/ngx_http_core_module.html)
* [ngx_http_ssl_module](http://nginx.org/en/docs/http/ngx_http_ssl_module.html) — The ngx_http_ssl_module module provides the necessary support for HTTPS
* [ngx_http_v2_module](https://nginx.org/en/docs/http/ngx_http_v2_module.html) — The ngx_http_v2_module module provides support for HTTP/2
* [ngx_http_realip_module](http://nginx.org/en/docs/http/ngx_http_realip_module.html) — The ngx_http_realip_module module is used to change the client address and optional port to the one sent in the specified header fields
* [ngx_http_addition_module](http://nginx.org/en/docs/http/ngx_http_addition_module.html) — The ngx_http_addition_module module is a filter that adds text before and after a response
* [ngx_http_xslt_module](http://nginx.org/en/docs/http/ngx_http_xslt_module.html) — The ngx_http_xslt_module is a filter that transforms XML responses using one or more XSLT stylesheet
* [ngx_http_image_filter_module](http://nginx.org/en/docs/http/ngx_http_image_filter_module.html) — The ngx_http_image_filter_module module is a filter that transforms images in JPEG, GIF, and PNG formats
* [ngx_http_geoip_module](http://nginx.org/en/docs/http/ngx_http_geoip_module.html) — The ngx_http_geoip_module module creates variables with values depending on the client IP address, using the precompiled MaxMind databases
* [ngx_http_sub_module](http://nginx.org/en/docs/http/ngx_http_sub_module.html) — The ngx_http_sub_module module is a filter that modifies a response by replacing one specified string by another
* [ngx_http_dav_module](http://nginx.org/en/docs/http/ngx_http_dav_module.html) — The ngx_http_dav_module module is intended for file management automation via the WebDAV protocol. The module processes HTTP and WebDAV methods PUT, DELETE, MKCOL, COPY, and MOVE
* [ngx_http_flv_module](http://nginx.org/en/docs/http/ngx_http_flv_module.html) — The ngx_http_flv_module module provides pseudo-streaming server-side support for Flash Video (FLV) files
* [ngx_http_mp4_module](http://nginx.org/en/docs/http/ngx_http_mp4_module.html) — The ngx_http_mp4_module module provides pseudo-streaming server-side support for MP4 files. Such files typically have the .mp4, .m4v, or .m4a filename extensions
* [ngx_http_gunzip_module](http://nginx.org/en/docs/http/ngx_http_gunzip_module.html) — The ngx_http_gunzip_module module is a filter that decompresses responses with “Content-Encoding: gzip” for clients that do not support “gzip” encoding method. The module will be useful when it is desirable to store data compressed to save space and reduce I/O costs
* [ngx_http_gzip_static_module](http://nginx.org/en/docs/http/ngx_http_gzip_static_module.html) — The ngx_http_gzip_static_module module allows sending precompressed files with the “.gz” filename extension instead of regular files
* [ngx_http_auth_request_module](http://nginx.org/en/docs/http/ngx_http_auth_request_module.html) — The ngx_http_auth_request_module module implements client authorization based on the result of a subrequest
* [ngx_http_random_index_module](http://nginx.org/en/docs/http/ngx_http_random_index_module.html) — The ngx_http_random_index_module module processes requests ending with the slash character (‘/’) and picks a random file in a directory to serve as an index file
* [ngx_http_secure_link_module](http://nginx.org/en/docs/http/ngx_http_secure_link_module.html) — The ngx_http_secure_link_module module (0.7.18) is used to check authenticity of requested links, protect resources from unauthorized access, and limit link lifetime
* [ngx_http_slice_module](https://nginx.org/en/docs/http/ngx_http_slice_module.html) — The ngx_http_slice_module module is a filter that splits a request into subrequests, each returning a certain range of response
* [ngx_http_stub_status_module](https://nginx.org/en/docs/http/ngx_http_stub_status_module.html) — The ngx_http_stub_status_module module provides access to basic status information
* [ngx_http_charset_module](http://nginx.org/en/docs/http/ngx_http_charset_module.html) — The ngx_http_charset_module module adds the specified charset to the “Content-Type” response header field
* [ngx_http_gzip_module](http://nginx.org/en/docs/http/ngx_http_gzip_module.html) — The ngx_http_gzip_module module is a filter that compresses responses using the “gzip” method
* [ngx_http_ssi_module](http://nginx.org/en/docs/http/ngx_http_ssi_module.html) — The ngx_http_ssi_module module is a filter that processes SSI (Server Side Includes) commands in responses passing through it
* [ngx_http_userid_module](http://nginx.org/en/docs/http/ngx_http_userid_module.html) — The ngx_http_userid_module module sets cookies suitable for client identification
* [ngx_http_access_module](http://nginx.org/en/docs/http/ngx_http_access_module.html) — The ngx_http_access_module module allows limiting access to certain client addresses
* [ngx_http_auth_basic_module](http://nginx.org/en/docs/http/ngx_http_auth_basic_module.html) — The ngx_http_auth_basic_module module allows limiting access to resources by validating the user name and password using the “HTTP Basic Authentication” protocol
* [ngx_http_autoindex_module](http://nginx.org/en/docs/http/ngx_http_autoindex_module.html) — The ngx_http_autoindex_module module processes requests ending with the slash character (‘/’) and produces a directory listing
* [ngx_http_geo_module](http://nginx.org/en/docs/http/ngx_http_geo_module.html) — The ngx_http_geo_module module creates variables with values depending on the client IP address
* [ngx_http_map_module](http://nginx.org/en/docs/http/ngx_http_map_module.html) — The ngx_http_map_module module creates variables whose values depend on values of other variables
* [ngx_http_split_clients_module](http://nginx.org/en/docs/http/ngx_http_split_clients_module.html) — The ngx_http_split_clients_module module creates variables suitable for A/B testing, also known as split testing
* [ngx_http_referer_module](http://nginx.org/en/docs/http/ngx_http_referer_module.html) — The ngx_http_referer_module module is used to block access to a site for requests with invalid values in the “Referer” header field
* [ngx_http_rewrite_module](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html) — The ngx_http_rewrite_module module is used to change request URI using PCRE regular expressions, return redirects, and conditionally select configurations
* [ngx_http_proxy_module](http://nginx.org/en/docs/http/ngx_http_proxy_module.html) — The ngx_http_proxy_module module allows passing requests to another server
* [ngx_http_fastcgi_module](http://nginx.org/en/docs/http/ngx_http_fastcgi_module.html) — The ngx_http_fastcgi_module module allows passing requests to a FastCGI server
* [ngx_http_uwsgi_module](http://nginx.org/en/docs/http/ngx_http_uwsgi_module.html) — The ngx_http_uwsgi_module module allows passing requests to a uwsgi server
* [ngx_http_scgi_module](http://nginx.org/en/docs/http/ngx_http_scgi_module.html) — The ngx_http_scgi_module module allows passing requests to an SCGI server
* [ngx_http_memcached_module](http://nginx.org/en/docs/http/ngx_http_memcached_module.html) — he ngx_http_memcached_module module is used to obtain responses from a memcached server
* [ngx_http_limit_conn_module](http://nginx.org/en/docs/http/ngx_http_limit_conn_module.html) — The ngx_http_limit_conn_module module is used to limit the number of connections per the defined key, in particular, the number of connections from a single IP address
* [ngx_http_limit_req_module](http://nginx.org/en/docs/http/ngx_http_limit_req_module.html) — he ngx_http_limit_req_module module is used to limit the request processing rate per a defined key, in particular, the processing rate of requests coming from a single IP address
* [ngx_http_empty_gif_module](http://nginx.org/en/docs/http/ngx_http_empty_gif_module.html) — The ngx_http_empty_gif_module module emits single-pixel transparent GIF
* [ngx_http_browser_module](http://nginx.org/en/docs/http/ngx_http_browser_module.html) — The ngx_http_browser_module module creates variables whose values depend on the value of the “User-Agent” request header field
* [ngx_http_upstream_module](http://nginx.org/en/docs/http/ngx_http_upstream_module.html) — http://nginx.org/en/docs/http/ngx_http_upstream_module.html
* [ngx_http_perl_module](http://nginx.org/en/docs/http/ngx_http_perl_module.html) — The ngx_http_perl_module module is used to implement location and variable handlers in Perl and insert Perl calls into SSI
* [ngx_mail_core_module](http://nginx.org/en/docs/mail/ngx_mail_core_module.html)
* [ngx_mail_ssl_module](http://nginx.org/en/docs/mail/ngx_mail_ssl_module.html) — The ngx_mail_ssl_module module provides the necessary support for a mail proxy server to work with the SSL/TLS protocol
* [ngx_mail_smtp_module](http://nginx.org/en/docs/mail/ngx_mail_smtp_module.html)
* [ngx_mail_imap_module](http://nginx.org/en/docs/mail/ngx_mail_imap_module.html)
* [ngx_mail_pop3_module](http://nginx.org/en/docs/mail/ngx_mail_pop3_module.html)
* [ngx_stream_core_module](http://nginx.org/en/docs/stream/ngx_stream_core_module.html)
* [ngx_stream_ssl_module](http://nginx.org/en/docs/stream/ngx_stream_ssl_module.html) — The ngx_stream_ssl_module module provides the necessary support for a stream proxy server to work with the SSL/TLS protocol
* [ngx_stream_proxy_module](http://nginx.org/en/docs/stream/ngx_stream_proxy_module.html) — The ngx_stream_proxy_module module allows proxying data streams over TCP, UDP, and UNIX-domain sockets

#### Third-party Nginx Modules

* [ngx_lua_ipc](https://github.com/slact/ngx_lua_ipc) — Interprocess communication for Lua Nginx Module and OpenResty — send named alerts with string data between Nginx worker processes
* [nchan](https://nchan.io/) ([Github](https://github.com/slact/nchan)) — Fast, horizontally scalable, multiprocess pub/sub queuing server and proxy for HTTP, long-polling, Websockets and EventSource (SSE)
* [ngx_pagespeed](http://ngxpagespeed.com/) ([Github](https://github.com/pagespeed/ngx_pagespeed)) — Automatic PageSpeed optimization module for Nginx
* [ModSecurity](https://www.modsecurity.org/) — Open Source Web Application Firewall
* [NAXSI](https://github.com/nbs-system/naxsi) — NAXSI is an open-source, high performance, low rules maintenance WAF for NGINX; NAXSI means Nginx Anti Xss & Sql Injection
* [nginx-upsync-module](https://github.com/weibocom/nginx-upsync-module) — Nginx C module, syncing upstreams from consul or others, dynamiclly adjusting backend servers weight, needn't reload nginx
* [sass-nginx-module](https://github.com/mneudert/sass-nginx-module) — Syntactically Awesome Nginx Module
* [More 3rd Party Modules](https://www.nginx.com/resources/wiki/modules/)

## Libraries

#### Core Libraries

Core Libraries are bundled in OpenResty package, and you don't need to separately install them.

* [lua-resty-core](https://github.com/openresty/lua-resty-core) — New FFI-based Lua API for the ngx_lua module
* [lua-resty-upstream-healthcheck](https://github.com/openresty/lua-resty-upstream-healthcheck) — Health Checker for Nginx Upstream Servers in Pure Lua
* [lua-resty-string](https://github.com/openresty/lua-resty-string) — String utilities and common hash functions for ngx_lua and LuaJIT
* [lua-resty-lock](https://github.com/openresty/lua-resty-lock) — Simple nonblocking lock API for ngx_lua based on shared memory dictionaries
* [lua-resty-lrucache](https://github.com/openresty/lua-resty-lrucache) — Lua-land LRU Cache based on LuaJIT FFI
* [lua-resty-dns](https://github.com/openresty/lua-resty-dns) — DNS resolver for the Nginx Lua module
* [lua-resty-resolver](https://github.com/jkeys089/lua-resty-resolver) — Caching DNS resolver for ngx_lua and LuaJIT
* [lua-resty-upload](https://github.com/openresty/lua-resty-upload) — Streaming reader and parser for HTTP file uploading based on ngx_lua cosocket
* [lua-resty-websocket](https://github.com/openresty/lua-resty-websocket) — Lua WebSocket implementation for the ngx_lua module
* [lua-resty-mysql](https://github.com/openresty/lua-resty-mysql) — Non-blocking Lua MySQL client driver for ngx_lua based on the cosocket API
* [lua-resty-memcached](https://github.com/openresty/lua-resty-memcached) — Lua memcached client driver for the ngx_lua based on the cosocket API
* [lua-resty-redis](https://github.com/openresty/lua-resty-redis) — Lua Redis client driver for the ngx_lua based on the cosocket API
* [lua-redis-parser](https://github.com/openresty/lua-redis-parser) — Redis reply parser and request constructor library for Lua
* [lua-rds-parser](https://github.com/openresty/lua-rds-parser) — Resty-DBD-Stream (RDS) parser for Lua written in C
* [lua-cjson](https://github.com/openresty/lua-cjson) — Lua cJSON is a fast JSON encoding / parsing module for Lua
* [lua-resty-shdict-simple](https://github.com/openresty/lua-resty-shdict-simple) — Simple applicaton-oriented interface to the OpenResty shared dictionary API
* [lua-resty-memcached-shdict](https://github.com/openresty/lua-resty-memcached-shdict) — Powerful memcached client with a shdict caching layer and many other features

#### Web Frameworks

* [Lapis](http://leafo.net/lapis/) — Lapis is a framework for building web applications using MoonScript or Lua that runs inside of a customized version of Nginx called OpenResty
* [lor](http://lor.sumory.com/) ([Github](https://github.com/sumory/lor)) — A fast and minimalist web framework based on OpenResty
* [Vanilla](https://github.com/idevz/vanilla) — An OpenResty Web Framework
* [luastar](https://github.com/luastar/luastar) — A HTTP server and web framework based on OpenResty
* [Lusty](https://github.com/Olivine-Labs/lusty) — Lua RESTful Web Application Framework, an extensible and speedy web framework
* [GIN](https://github.com/ostinelli/gin) — A fast, low-latency, low-memory footprint, web JSON-API framework with Test Driven Development helpers and patterns
* [Quick Server](https://github.com/dualface/quickserver) — A Server Framework Based on OpenResty
* [Sailor](https://github.com/sailorproject/sailor) — A Lua MVC Web Framework
* [lua-resty-rack](https://github.com/pintsized/lua-resty-rack) — A simple and extensible HTTP server framework for OpenResty
* [MOOCHINE](https://github.com/appwilldev/moochine) — A simple and lightweight web framework based on OpenResty
* [sinatra-openresty](https://github.com/jtarchie/sinatra-openresty) — Sinatra ported to OpenResty framework
* [lj-web](https://github.com/kindy/lj-web) — Lightweight Web Framework Based On ngx_openresty
* [Gimlet Cocktail](https://github.com/losinggeneration/gimlet) — A micro web application framework for OpenResty written in Moonscript inspired by Martini & Sinatra
* [durap](https://github.com/doujiang24/durap) — Durap is a Lua Web Framework based on OpenResty.
* [Ziggy Stardust](https://github.com/bakins/stardust) — Ziggy Stardust (or just "stardust") is a simple nginx/Lua framework inspired by Sinatra, Express, and Mercury
* [zLua](https://github.com/mrxx/zLua) — A Codeigniter like Lua framework based on OpenResty
* [lua-resty-stack](https://github.com/antonheryanto/lua-resty-stack) — OpenResty Simple Application Stack
* [dodolu](https://github.com/zhangf911/dodolu) — A lightweight web framework based on OpenResty
* [Octopus](https://github.com/cyberz-eu/octopus) ([Github](https://github.com/cyberz-eu/octopus)) — The Lua Web Platform
* [vicky](https://github.com/RocksonZeta/vicky) — A restful framework for openresty,inspired by expressjs and koa.

#### Web Development Essentials

* [lua-resty-cookie](https://github.com/cloudflare/lua-resty-cookie) — Lua library for HTTP cookie manipulations for OpenResty/ngx_lua
* [lua-resty-cors](https://github.com/detailyang/lua-resty-cors) — The Cross-Origin Resource Sharing (CORS) implementation for OpenResty
* [lua-resty-session](https://github.com/bungle/lua-resty-session) — Session library for OpenResty implementing Secure Cookie Protocol
* [lua-resty-woothee](https://github.com/woothee/lua-resty-woothee) — The Lua-Openresty implementation of Project Woothee, which is a multi-language user-agent strings parsers
* [lua-resty-mobile](https://github.com/isage/lua-resty-mobile) — This library parses HTTP headers and detects mobile device
* [lua-resty-jwt](https://github.com/SkyLothar/lua-resty-jwt) — JWT (JSON Web Tokens) for The Great OpenResty
* [neturl](https://github.com/golgote/neturl) — URL and Query string parser, builder, normalizer for Lua
* [Mio](https://github.com/iresty/Mio) — API statistics/summary and health datas in NGINX based on OpenResty, just like NGINX Plus

#### Routing Libraries

* [lua-resty-route](https://github.com/bungle/lua-resty-route) — A URL routing library for OpenResty supporting multiple route matchers, middleware, and HTTP and WebSockets handlers to mention a few of its features 
* [router.lua](https://github.com/APItools/router.lua) — A barebones router for Lua, it matches URLs and executes Lua functions
* [lua-resty-r3](https://github.com/toritori0318/lua-resty-r3) — [libr3](https://github.com/c9s/r3) OpenResty implementation, libr3 is a high-performance path dispatching library. It compiles your route paths into a prefix tree (trie). By using the constructed prefix trie in the start-up time, you may dispatch your routes with efficiency

#### Request Argments Parsers

* [lua-resty-reqargs](https://github.com/bungle/lua-resty-reqargs) — Helper to Retrieve application/x-www-form-urlencoded, multipart/form-data, and application/json Request Arguments
* [lua-resty-post](https://github.com/antonheryanto/lua-resty-post) — HTTP Post Utility for OpenResty (File Uploading Helper)
* [lua-resty-multipart-parser](https://github.com/agentzh/lua-resty-multipart-parser) — Simple multipart data parser for OpenResty / Lua
* [lua-resty-multipart](https://github.com/thibaultcha/lua-resty-multipart) — Multipart parsing library for OpenResty

#### Middleware and API Tools

* [Kong](https://getkong.org/) ([GitHub](https://github.com/Kong/kong)) — KONG: Microservice Management Layer (Secure, Manage & Extend your APIs and Microservices)
* [LSSO](https://github.com/maiome-development/lsso) — A Lightweight SSO middleware for Nginx + Lua
* [apigateway](https://github.com/adobe-apiplatform/apigateway) — A Performant API Gateway based on Nginx and OpenResty

#### Templating

* [lua-resty-template](https://github.com/bungle/lua-resty-template) — A Compiling (HTML) templating engine for Lua and OpenResty
* [lemplate](https://github.com/openresty/lemplate) — OpenResty/Lua template framework implementing Perl's TT2 templating language
* [etlua](https://github.com/leafo/etlua) — Embedded Lua templates
* [liquid-lua](https://github.com/chenxianyu2015/liquid-lua) — A Lua implementation of Liquid for OpenResty platform
* [lua-resty-tmpl](https://github.com/lloydzhou/lua-resty-tmpl) — A simple template engine for Lua and OpenResty, derived from [lua-template](https://github.com/dannote/lua-template).
* [Alternatives](https://github.com/bungle/lua-resty-template#alternatives) — Some alternative Lua templating solutions that may work just fine with OpenResty

#### Validation

* [lua-resty-validation](https://github.com/bungle/lua-resty-validation) — An extendable chaining validation and filtering library for Lua and OpenResty
* [valua](https://github.com/sailorproject/valua) — Validation for lua! A module for making chained validations. Create your objects, append your tests, use and reuse it!

#### Authentication and Authorization

* [lua-resty-macaroons](https://github.com/bungle/lua-resty-macaroons) — LuaJIT FFI Bindings to libmacaroons – Macaroons are flexible authorization credentials that support decentralized delegation, attenuation, and verification
* [lua-resty-openidc](https://github.com/pingidentity/lua-resty-openidc) — lua-resty-openidc is a library for NGINX implementing the OpenID Connect Relying Party (RP) and the OAuth 2.0 Resource Server (RS) functionality
* [micro-auth](https://github.com/hypebeast/micro-auth) — A microservice that makes adding authentication with Google and Github to your application easy (Note: before using it in production, see: https://news.ycombinator.com/item?id=13682682 — hopefully we can remove this remark in a future)

#### Cryptography

* [lua-resty-string](https://github.com/openresty/lua-resty-string) — String utilities and common hash functions for ngx_lua and LuaJIT
* [lua-resty-nettle](https://github.com/bungle/lua-resty-nettle) — LuaJIT FFI bindings for Nettle (a low-level cryptographic library)
* [lua-resty-chash](https://github.com/agentzh/lua-resty-chash) — A generic consistent hash implementation for OpenResty/Lua
* [lua-resty-jump-consistent-hash](https://github.com/ruoshan/lua-resty-jump-consistent-hash) — Jump Consistent Hash for LuaJIT
* [lua-resty-letsencrypt](https://github.com/torhve/lua-resty-letsencrypt) — Automatically fetch and renew TLS certificates on the fly using LetsEncrypt CA.
* [lua-resty-auto-ssl](https://github.com/GUI/lua-resty-auto-ssl) — On the fly (and free) SSL registration and renewal inside OpenResty/nginx with Let's Encrypt
* [lua-resty-murmurhash2](https://github.com/bungle/lua-resty-murmurhash2) — LuaJIT MurmurHash 2 bindings to Nginx / OpenResty murmurhash2 implementation
* [lua-resty-hmac](https://github.com/jamesmarlowe/lua-resty-hmac) — Lua driver for making and receiving hmac signed requests
* [lua-resty-scrypt](https://github.com/bungle/lua-resty-scrypt) — LuaJIT FFI-based scrypt library for OpenResty
* [lua-resty-xxhash](https://github.com/bungle/lua-resty-xxhash) — LuaJIT FFI-bindings to xxHash, an Extremely fast non-cryptographic hash algorithm
* [lua-resty-rsa](https://github.com/doujiang24/lua-resty-rsa) — RSA functions for LuaJIT
* [lua-resty-aead](https://github.com/tmthrgd/lua-resty-aead) — AEAD cipher library for lua-nginx-module. BoringSSL only.
* [lua-resty-hawk](https://github.com/golgote/lua-resty-hawk) — Hawk authentication on Nginx with Lua and OpenResty
* [lua-resty-urandom](https://github.com/p0pr0ck5/lua-resty-urandom) — Buffered wrapper for Linux/BSD kernel space CSPRNG
* [lua-resty-fastpbkdf2](https://github.com/mynameiscfed/lua-resty-fastpbkdf2) — Lua bindings to fastpbkdf2
* [lua-argon2-ffi](https://github.com/thibaultCha/lua-argon2-ffi) — LuaJIT FFI binding for the Argon2 password hashing algorithm
* [lua-resty-des](https://github.com/lilien1010/lua-resty-des) — Lua interface to make DES ECB encryption

#### Networking

* [lua-resty-http](https://github.com/pintsized/lua-resty-http) by [@pintsized](https://github.com/pintsized) — Lua HTTP client cosocket driver for OpenResty / ngx_lua
* [lua-resty-http](https://github.com/liseen/lua-resty-http) by [@liseen](https://github.com/liseen) — Lua http client driver for the ngx_lua based on the cosocket API
* [lua-resty-http](https://github.com/DorianGray/lua-resty-http) by [@DorianGray](https://github.com/DorianGray) — Lua HTTP client driver for ngx_lua based on the cosocket API
* [lua-resty-http-simple](https://github.com/bakins/lua-resty-http-simple) — Simple Lua HTTP client driver for ngx_lua
* [lua-resty-httpipe](https://github.com/timebug/lua-resty-httpipe) — Lua HTTP client cosocket driver for OpenResty / ngx_lua
* [lua-resty-httpclient](https://github.com/oneoo/lua-resty-httpclient) — Nonblocking Lua HTTP Client library for aLiLua & ngx_lua
* [lua-httpcli-resty](https://github.com/mah0x211/lua-httpcli-resty) — Lua HTTP client module for OpenResty
* [lua-resty-websocket](https://github.com/openresty/lua-resty-websocket) — Lua WebSocket implementation for the ngx_lua module
* [lua-resty-mediador](https://github.com/Kong/lua-resty-mediador) — Determines address of proxied request and does IP address / CIDR blocks handling (both IPv4 and IPv6)
* [lua-resty-iputils](https://github.com/hamishforbes/lua-resty-iputils) — Utility functions for working with IP addresses in OpenResty
* [lua-resty-readurl](https://github.com/jamesmarlowe/lua-resty-readurl) — Lua library for capturing urls, decoding, and logging results
* [lua-resty-dns-client](https://github.com/Kong/lua-resty-dns-client) — Lua library containing a DNS client, several utilities, and a load-balancer
* [lua-resty-upstream](https://github.com/hamishforbes/lua-resty-upstream) — Upstream connection load balancing and failover module
* [lua-resty-checkups](https://github.com/upyun/lua-resty-checkups) — Manage Nginx upstreams in pure ngx_lua
* [lua-resty-socks5](https://github.com/starius/lua-resty-socks5) — Lua SOCKS5 client for the ngx_lua based on the cosocket API
* [lua-resty-waf](https://github.com/p0pr0ck5/lua-resty-waf) — High-performance WAF built on the OpenResty stack
* [lua-resty-tarpit](https://github.com/p0pr0ck5/lua-resty-tarpit) — OpenResty response time inflation, capture and delay unwanted requests
* [lua-resty-jsonrpc-batch](https://github.com/mosasiru/lua-resty-jsonrpc-batch) — JSON-RPC 2.0 Batch Request protocol module for OpenResty
* [lua-resty-limit-traffic](https://github.com/openresty/lua-resty-limit-traffic) — Lua library for limiting and controlling traffic in OpenResty/ngx_lua
* [lua-resty-limits](https://github.com/membphis/lua-resty-limits) — Limits request every second or minute
* [lua-resty-fastcgi](https://github.com/benagricola/lua-resty-fastcgi) — Lua FCGI client driver for ngx_lua based on the cosocket API
* [lua-resty-ftpclient](https://github.com/Ahsialh/lua-resty-ftpclient) — Lua FTP client driver for the ngx_lua based on the cosocket API
* [lua-capnproto](https://github.com/cloudflare/lua-capnproto) — Cap’n Proto is an insanely fast data interchange format and capability-based RPC system
* [lua-resty-tornera](https://github.com/pinge/lua-resty-tornera) — A traffic replay tool with an easy to use HTTP API for OpenResty / LuaJIT
* [lua-resty-consul](https://github.com/hamishforbes/lua-resty-consul) — Library to interface with the consul HTTP API from ngx_lua
* [lua-resty-healthcheck](https://github.com/Kong/lua-resty-healthcheck) — Healthcheck library for OpenResty to validate upstream service status

#### Databases and Storages

* [lua-resty-mysql](https://github.com/openresty/lua-resty-mysql) — Non-blocking Lua MySQL client driver for ngx_lua based on the cosocket API
* [lua-resty-postgres](https://github.com/azurewang/lua-resty-postgres) — Nonblocking Lua PostgreSQL driver library for ngx_lua
* [pgmoon](https://github.com/leafo/pgmoon) — A pure Lua Postgres driver for use in OpenResy & more
* [lua-resty-couchbase](https://github.com/ZigzagAK/lua-resty-couchbase) — OpenResty CouchBase module
* [lua-resty-couchdb](https://github.com/paragasu/lua-resty-couchdb) — Lua resty minimal couchdb client using nginx proxy ngx.location_capture
* [lua-resty-orm](https://github.com/kran/lua-resty-orm) — Simple ORM for OpenResty
* [lua-resty-mvc](https://github.com/pronan/lua-resty-mvc) — You don't need that complicated MVC framework! With just a plain folder with several simple files, you can enjoy basic but most frequently used MVC features.
* [lua-resty-memcached](https://github.com/openresty/lua-resty-memcached) — Lua memcached client driver for the ngx_lua based on the cosocket API
* [lua-resty-redis](https://github.com/openresty/lua-resty-redis) — Lua Redis client driver for the ngx_lua based on the cosocket API
* [lua-resty-redis-connector](https://github.com/pintsized/lua-resty-redis-connector) — Connection utilities for lua-resty-redis, making it easy and reliable to connect to Redis hosts, either directly or via Redis Sentinel
* [resty-redis-cluster](https://github.com/steve0511/resty-redis-cluster) — OpenResty Redis cluster-aware client based on resty-redis-cluster
* [lua-resty-redis-cluster](https://github.com/cuiweixie/lua-resty-redis-cluster) — OpenResty Redis Cluster Client
* [lua-cassandra](https://github.com/thibaultCha/lua-cassandra) - Pure Lua, feature-rich, and cluster-aware Cassandra client
* [lua-resty-cassandra](https://github.com/jbochi/lua-resty-cassandra) — Pure Lua Cassandra client using CQL binary protocol
* [lua-resty-bloomd](https://github.com/jie123108/lua-resty-bloomd) — A client library based on ngx_lua to interface with [bloomd servers](https://github.com/armon/bloomd)
* [lua-resty-riak](https://github.com/bakins/lua-resty-riak) — Lua riak protocol buffer client driver for the ngx_lua based on the cosocket API
* [lua-resty-moongoo](https://github.com/isage/lua-resty-moongoo) — MongoDB library for OpenResty, highly inspired by Perl Mango
* [lua-resty-mongol](https://github.com/Olivine-Labs/resty-mongol/) — Native Lua Mongodb driver which supports both luasocket and ngx_lua based on the cosocket API
* [lua-resty-mongo](https://github.com/nightsailer/lua-resty-mongo) — Lua mongodb client driver for the ngx_lua based on the cosocket API
* [lua-mongo](https://github.com/boyxuper/lua-mongo) — A simple Lua Mongo driver (a fork made to work with co-sockets)
* [lua-resty-influx](https://github.com/p0pr0ck5/lua-resty-influx) — OpenResty client for InfluxDB
* [lua-resty-kyototycoon](https://github.com/cloudflare/lua-resty-kyototycoon) — Lua client driver for KyotoTycoon using its native wire protocol (OpenResty/ngx_lua)
* [lua-resty-kyototycoon](https://github.com/sjnam/lua-resty-kyototycoon) — Lua client driver for KyotoTycoon using its binary protocol
* [lua-resty-tarantool](https://github.com/perusio/lua-resty-tarantool) — Library for working with Tarantool from Nginx with the embedded Lua module or with OpeRresty
* [lua-nginx-tarantool](https://github.com/ziontab/lua-nginx-tarantool) — A driver for a NoSQL database in a Lua script Tarantool build on fast nginx cosockets
* [lua-resty-ssdb](https://github.com/LazyZhu/lua-resty-ssdb) — Lua ssdb client driver for the ngx_lua based on the cosocket API, SSDB is a leveldb server
* [ledis-openresty](https://github.com/holys/ledis-openresty) — Lua LedisDB client driver for the ngx_lua based on the cosocket API
* [lua-resty-fastdfs](https://github.com/azurewang/lua-resty-fastdfs) — Nonblocking Lua FastDFS driver library for ngx_lua
* [lua-resty-statsd](https://github.com/mediba-system/lua-resty-statsd) — StatsD client for OpenResty
* [lua-resty-dogstatsd](https://github.com/mediba-system/lua-resty-dogstatsd) — A client for DogStatsD, an extension of the StatsD metric server for Datadog. Using nginx cosocket API
* [openresty-statsd](https://github.com/lonelyplanet/openresty-statsd) — A Lua module for OpenResty to send metrics to StatsD
* [lua-resty-mogilefs](https://github.com/sunkan/lua-resty-mogilefs) — A Lua mogilefs client driver for the ngx_lua based on the cosocket API

#### Testing and Profiling

* [Test::Nginx](http://search.cpan.org/~agent/Test-Nginx-0.24/lib/Test/Nginx.pm) — Data-driven test scaffold for Nginx C module and OpenResty Lua library development (see real-word tests in [lua-resty-redis](https://github.com/openresty/lua-resty-redis/tree/master/t))
* [nginx-systemtap-toolkit](https://github.com/openresty/nginx-systemtap-toolkit) — Real-time analyzing and diagnosing tools for Nginx based on SystemTap
* [stapxx](https://github.com/openresty/stapxx) — Simple macro language extentions to systemtap
* [FlameGraph](https://github.com/brendangregg/FlameGraph) — Flame graphs are a visualization of profiled software, allowing the most frequent code-paths to be identified quickly and accurately
* [lua-resty-busted](https://github.com/thibaultCha/lua-resty-busted) — Test OpenResty scripts with busted
* [lua-resty-test](https://github.com/membphis/lua-resty-test) — Test frame based on OpenResty
* [busted](http://olivinelabs.com/busted/) ([Github](https://github.com/Olivine-Labs/busted)) — Elegant Lua unit testing
* [Telescope](http://telescope.luaforge.net/) ([Github](https://github.com/norman/telescope)) — Telescope is a highly customizable test library for Lua that allows for declarative tests with nested contexts

#### Message Queuing and Task Management

* [lua-resty-qless](https://github.com/pintsized/lua-resty-qless) — Lua binding to Qless (Queue / Pipeline management) for OpenResty (see also: [Qless Web Interface](https://github.com/hamishforbes/lua-resty-qless-web) implemented with OpenResty)
* [lua-resty-rabbitmqstomp](https://github.com/wingify/lua-resty-rabbitmqstomp) — Lua RabbitMQ client library which uses cosocket api for communication over STOMP 1.2 with a RabbitMQ broker which has the STOMP plugin
* [lua-resty-gearman](https://github.com/zhhchen/lua-resty-gearman) — Lua gearman client driver for the ngx_lua based on the cosocket API
* [lua-resty-kafka](https://github.com/doujiang24/lua-resty-kafka) — Lua kafka client driver for the ngx_lua based on the cosocket API
* [lua-resty-beanstalkd](https://github.com/bakins/lua-resty-beanstalkd) — Lua beanstalkd client driver for the ngx_lua based on the cosocket API
* [lua-resty-ironmq](https://github.com/bakins/lua-resty-ironmq) — Simple IronMQ client for OpenResty

#### Bar Codes and QR Codes

* [lua-resty-QRcode](https://github.com/dcshi/lua-resty-QRcode) — QR encode tool for ngx_lua
* [lua-resty-QRDecode](https://github.com/dcshi/lua-resty-QRDecode) — QR decoder for ngx_lua

#### Utilities

* [lua-resty-worker-manager](https://github.com/Kong/lua-resty-worker-manager) — Tracks worker processes and nodes starting / restarting / reloading / stopping
* [lua-resty-worker-events](https://github.com/Kong/lua-resty-worker-events) — Inter process events for Nginx worker processes
* [lua-resty-batch](https://github.com/starius/lua-resty-batch) — Merge multiple requests in nginx to a single sub-request
* [lua-resty-shell](https://github.com/juce/lua-resty-shell) — Tiny non-blocking subprocess / shell library to use with OpenResty application server (using [sockproc](https://github.com/juce/sockproc))
* [lua-resty-exec](https://github.com/jprjr/lua-resty-exec) — Non-blocking, non-shell-spawning, streaming and non-streaming subprocess library (using [sockexec](https://github.com/jprjr/sockexec))
* [lua-resty-repl](https://github.com/saks/lua-resty-repl) — Interactive console (REPL) for OpenResty and LuaJIT code
* [lua-resty-fileinfo](https://github.com/bungle/lua-resty-fileinfo) — LuaJIT FFI bindings to libmagic, magic number recognition library - tries to determine file types
* [lua-resty-taglib](https://github.com/bungle/lua-resty-taglib) - LuaJIT FFI bindings for TagLib - An Audio Meta-Data Library
* [lua-resty-uuid](https://github.com/bungle/lua-resty-uuid) — LuaJIT FFI bindings for libuuid, a DCE compatible Universally Unique Identifier library
* [lua-resty-jit-uuid](https://github.com/thibaultCha/lua-resty-jit-uuid) — A pure LuaJIT (no dependencies) uuid generator tuned for performance
* [lua-resty-tsort](https://github.com/bungle/lua-resty-tsort) — Performs a topological sort on input data
* [lua-resty-postal](https://github.com/bungle/lua-resty-postal) — LuaJIT FFI Bindings to libpostal – a fast statistical parser/normalizer for street addresses around the world.
* [lua-resty-libinjection](https://github.com/p0pr0ck5/lua-resty-libinjection) — LuaJIT FFI bindings for libinjection, a SQL/SQLi tokenizer and analyzer
* [lua-resty-socket](https://github.com/thibaultcha/lua-resty-socket) - Automatic LuaSocket/cosockets compatibility module
* [Inspect](https://github.com/kikito/inspect.lua) ([Github](https://github.com/kikito/inspect.lua)) — Inspect is a library that transforms any Lua value into a human-readable representation. It is especially useful for debugging errors in tables.
* [lua-resty-maxminddb](https://github.com/lilien1010/lua-resty-maxminddb) ([Github](https://github.com/lilien1010/lua-resty-maxminddb)) — LuaJIT FFI Bindings to official libmaxminddb, to get ip location with ip database offered by maxmind

#### Date and Time

These libraries are not build to using `lua-nginx-module`s date time functions (except luatz) like [`ngx.today`](https://github.com/openresty/lua-nginx-module#ngxtoday), [`ngx.time`](https://github.com/openresty/lua-nginx-module#ngxtime), [`ngx.now`](https://github.com/openresty/lua-nginx-module#ngxnow), [`ngx.localtime`](https://github.com/openresty/lua-nginx-module#ngxlocaltime), or [`ngx.utctime`](https://github.com/openresty/lua-nginx-module#ngxutctime), but they may still come handy. At some point we may need a more "official" time library for OpenResty.

* [luatz](https://github.com/daurnimator/luatz) — A Lua library for time and date manipulation (has a fallback to `ngx.now`)
* [LuaDate](https://github.com/Tieske/date) — Lua Date and Time module for Lua 5.x
* [SciLua Time Library](http://scilua.org/time.html) — Library for the manipulation of dates and periods according to the Gregorian calendar, i.e. the internationally accepted calendar for most uses

#### Compression

* [lua-resty-zip](https://github.com/doujiang24/lua-resty-zip) — ZIP functions(compress/uncompress) for LuaJIT
* [lua-resty-snappy](https://github.com/bungle/lua-resty-snappy) — LuaJIT FFI bindings for Snappy, a fast compressor/decompressor
* [lua-resty-brotli](https://github.com/sjnam/lua-resty-brotli) — LuaJIT FFI bindings for Google Brotli
* [lua-resty-zstd](https://github.com/sjnam/lua-resty-zstd) —  LuaJIT bindings to Facebook Zstandard using FFI

#### Text Formats

* [lua-resty-hoedown](https://github.com/bungle/lua-resty-hoedown) — LuaJIT FFI bindings to Hoedown, a standards compliant, fast, secure markdown processing library in C
* [lua-gumbo](https://github.com/craigbarnes/lua-gumbo) — Lua bindings for the Gumbo HTML5 parsing library, with a set of DOM APIs implemented in pure Lua
* [lua-resty-sass](https://github.com/bungle/lua-resty-sass) — LuaJIT FFI bindings for libsass - A C/C++ implementation of a Sass compiler (http://libsass.org/).
* [lua-resty-lanli](https://github.com/bungle/lua-resty-lanli) — LuaJIT FFI Bindings to Lanli HTML Sanitizer Library
* [lua-resty-ini](https://github.com/doujiang24/lua-resty-ini) —  Lua INI-file parser
* [lua-re2](https://github.com/cloudflare/lua-re2) — C and Lua wrapper for RE2 regular expression library.
* [lua-aho-corasick](https://github.com/cloudflare/lua-aho-corasick) — C++ and Lua Implementation of the Aho-Corasick (AC) string matching algorithm
* [lua-resty-json](https://github.com/cloudflare/lua-resty-json) — JSON library for Lua and C (decoder only).
* [lua-resty-libcjson](https://github.com/bungle/lua-resty-libcjson) — LuaJIT FFI-based cJSON library for OpenResty
* [lua-resty-prettycjson](https://github.com/bungle/lua-resty-prettycjson) — Lua cJSON Pretty Formatter
* [lua-resty-utf8rewind](https://github.com/bungle/lua-resty-utf8rewind) — LuaJIT FFI bindings for utf8rewind - a system library written in C designed to extend the default string handling functions with support for UTF-8 encoded text
* [lua-resty-unistring](https://github.com/bungle/lua-resty-unistring) — LuaJIT FFI bindings for GNU libunistring - A Unicode string manipulation lIbrary (https://www.gnu.org/software/libunistring/)
* [lua-resty-htmlentities](https://github.com/detailyang/lua-resty-htmlentities) — Backport the entities to LuaJIT with the FFI binding as the entities to UTF-8 decoder
* [lua-resty-jsdecode](https://github.com/detailyang/lua-resty-jsdecode) — Javascript Escape Notation decoding to UTF-8 bytes

#### Binary Formats

* [lua-resty-msgpack](https://github.com/chronolaw/lua-resty-msgpack) — Lua Message Pack for OpenResty
* [luajit-msgpack-pure](https://github.com/catwell/luajit-msgpack-pure) — MessagePack for LuaJIT (using FFI, no bindings, V4 API)

#### Document Formats

* [lua-resty-libxl](https://github.com/bungle/lua-resty-libxl) — LuaJIT FFI-based LibXL (Excel) library for OpenResty
* [lua-resty-haru](https://github.com/bungle/lua-resty-haru) — LuaJIT FFI-based libHaru (PDF) library for OpenResty
* [lua-resty-hpdf](https://github.com/tavikukko/lua-resty-hpdf) — LuaJIT FFI-based libHaru (PDF) library for OpenResty

#### Image Formats

* [Lua IMagick](https://github.com/isage/lua-imagick) — Lua Pure-C Bindings to ImageMagick
* [magick](https://github.com/leafo/magick) — Lua Bindings to ImageMagick for LuaJIT using FFI
* [giflib](https://github.com/leafo/giflib) — Lua bindings to GIFLIB for LuaJIT using FFI
* [fi-luajit](https://github.com/nyfair/fi-luajit) — A LuaJIT interface to FreeImage

#### Localization

* [lua-resty-gettext](https://github.com/bungle/lua-resty-gettext) — LuaJIT FFI-based gettext library for OpenResty

#### Caching

* [lua-resty-lrucache](https://github.com/openresty/lua-resty-lrucache) — Lua-land LRU Cache based on LuaJIT FFI
* [shcache](https://github.com/mtourne/ngx.shcache) — shcache is an attempt at using ngx.shared.DICT with a caching state machine layed on top
* [lua-resty-tlc](https://github.com/hamishforbes/lua-resty-tlc) — Two Layer Cache implementation using lua-resty-lrucache and shared dictionaries.
* [Ledge](https://github.com/pintsized/ledge) — A Lua application for OpenResty, providing HTTP cache functionality for Nginx, using Redis as a cache / metadata store
* [lua-resty-cache](https://github.com/lloydzhou/lua-resty-cache) — HTTP Cache to Redis, can serve stale response, and using `lua-resty-lock` only allow one request to populate a new cache

#### Metrics and Statistics

* [LUAMETER](https://luameter.com/) — A Lua module for Nginx that records and provides key status and performance metrics, right from within Nginx and in real-time (Proprietary)
* [ngxtop](https://github.com/lebinh/ngxtop) — Real-Time metrics for nginx server

#### Logging

* [lua-resty-logger-socket](https://github.com/cloudflare/lua-resty-logger-socket) — Raw-socket-based Logger Library for Nginx (based on ngx_lua)
* [raven-lua](https://github.com/cloudflare/raven-lua) — A small Lua interface to Sentry
* [lua-nginx-logging](https://github.com/Lumate/lua-nginx-logging) — Logging utilities for Nginx written in Lua
* [lua-resty-logger](https://github.com/kedyyan/lua-resty-logger) — Custom Logger Library for OpenResty
* [lua-resty-rfc5424](https://github.com/detailyang/lua-resty-rfc5424) — An implementation of the RFC5424(syslog) in the OpenResty
* [lua-resty-fluentd](https://github.com/msempere/lua-resty-fluentd) — Lua fluentd logger for the ngx_lua based on the cosocket API
* [lua-resty-fluent-logger](https://github.com/mediba-system/lua-resty-fluent-logger) — A structured logger for Fluentd (OpenResty / ngx_lua)
* [raven-lua](https://github.com/cloudflare/raven-lua) — A small Lua interface to Sentry that also has a helpful wrapper function call() that takes any arbitrary Lua function (with arguments) and executes it, traps any errors and reports it automatically to Sentry

#### Functional Programming

* [Lua Fun](https://github.com/rtsisyk/luafun) — Lua Fun is a high-performance functional programming library for Lua designed with LuaJIT's trace compiler in mind
* [Penlight](https://github.com/stevedonovan/Penlight) — Penlight brings together a set of generally useful pure Lua modules, focusing on input data handling (such as reading configuration files), functional programming (such as map, reduce, placeholder expressions, etc), and OS path management
* [Moses](https://github.com/Yonaba/Moses) — A Lua utility-belt library for functional programming. It complements the built-in Lua table library, making easier operations on arrays, lists, collections
* [Underscore.lua](https://github.com/mirven/underscore.lua) — Underscore.lua is a Lua library that provides a set of utility functions for dealing with iterators, arrays, tables, and functions
* [Lodash.lua](https://github.com/axmat/lodash.lua) — A functional programming library for Lua in respect to the Javascript library Lodash
* [Search for more "Functional Lua" projects on GitHub...](https://github.com/search?l=Lua&o=desc&q=lua+functional&s=stars&type=Repositories&utf8=%E2%9C%93)

#### Web APIs

* [lua-resty-github](https://github.com/jamesmarlowe/lua-resty-github) — Lua library for using the github api in the ngx_lua nginx module
* [lua-resty-hipchat](https://github.com/jamesmarlowe/lua-resty-hipchat) — Lua library for using the hipchat api
* [lua-resty-newrelic](https://github.com/saks/lua-resty-newrelic) — Lua newrelic SDK for the ngx_lua based on the C SDK
* [api-gateway-aws](https://github.com/adobe-apiplatform/api-gateway-aws) — Lua module for AWS APIs. The missing AWS SDK from Nginx / OpenResty. Use it to proxy AWS APIs in a simple fashion, with any HTTP Client that you prefer.
* [lua-resty-aws](https://github.com/grosskur/lua-resty-aws) — AWS signature V4 library for OpenResty + Lua
* [lua-resty-aws-sdk](https://github.com/kiddkai/lua-resty-aws-sdk) — A raw AWS SDK generated from API specification
* [lua-resty-aws-email](https://github.com/paragasu/lua-resty-aws-email) — Send email using Amazon Simple Email Service(SES) API
* [lua-resty-aws-auth](https://github.com/paragasu/lua-resty-aws-auth) — Simple Lua resty utilities to generate Amazon v4 authorization and signature headers
* [lua-resty-s3](https://github.com/jamesmarlowe/lua-resty-s3) — Lua driver for uploading content to Amazon S3
* [lua-resty-s3uploader](https://github.com/lilien1010/lua-resty-s3uploader) — An AWS S3 upload client，easy to use
* [lua-resty-paypal](https://github.com/Chewbye/lua-resty-paypal) — Lua Paypal client using express checkout for OpenResty
* [lua-resty-17monip](https://github.com/timebug/lua-resty-17monip) — 17MonIP parsing library for ngx_lua
* [lua-resty-upyun](https://github.com/aCayF/lua-resty-upyun) — Upyun cloud-based platform
* [lua-resty-newrelic](https://github.com/saks/lua-resty-newrelic) — New Relic bindings for a OpenResty / Lua
* [lua-mailgun](https://github.com/leafo/lua-mailgun) — A Lua library for sending emails and interacting with the Mailgun API. Compatible with OpenResty via Lapis HTTP API, or any other Lua script via LuaSocket.
* [lua-payments](https://github.com/leafo/lua-payments) — Bindings to various payment provider APIs for use in Lua (with OpenResty or anything that supports LuaSocket)

#### Other Sources for Libraries

* [OpenResty Package Manager Repository](https://opm.openresty.org/)
* [LuaRocks Repository](https://luarocks.org/) ([Search for *resty* libraries in LuaRocks](https://luarocks.org/search?q=resty&non_root=on))
* [Github Search for lua-resty-* Libraries](https://github.com/search?o=desc&q=lua-resty+in%3Aname&ref=searchresults&s=stars&type=Repositories&utf8=%E2%9C%93), or [the recently updated ones](https://github.com/search?o=desc&q=lua-resty+in%3Aname&ref=searchresults&s=updated&type=Repositories&utf8=%E2%9C%93)
* [Lua Toolbox](https://lua-toolbox.com/)
* [luapower — Lua, JIT, batteries](https://luapower.com/)
* [List of Available LuaJIT Packages](http://wiki.luajit.org/FFI-Native-Libraries)
* [List of Available LuaJIT FFI Bindings](http://wiki.luajit.org/FFI-Bindings)

## Books and Tutorials

#### Books

* [Programming OpenResty](https://www.gitbook.com/book/openresty/programming-openresty/details) — Scripting an NGINX-based Web Platform (Work-in-Progress)
* [OpenResty Best Practices](https://github.com/moonbingbing/openresty-best-practices) ([GitBook](https://www.gitbook.com/book/moonbingbing/openresty-best-practices/details)) (Chinese, use e.g. Google Translate)

#### Tutorials and Guides

* [agentzh's Nginx Tutorials](http://openresty.org/download/agentzh-nginx-tutorials-en.html)
* [Definitely an OpenResty Guide](http://www.staticshin.com/programming/definitely-an-open-resty-guide/)
* [Top ten things about OpenResty](http://www.staticshin.com/top-tens/things-about-openresty.html)
* The Latest and Greatest from ngx_lua: New Features & Tools ([Summary](https://nginx.busyconf.com/activities/53d854c1c9e255cf2d00007b), [Slides](http://agentzh.org/misc/slides/nginx-conf-2014/#1), [PDF](http://agentzh.org/misc/slides/nginx-conf-2014.pdf), [Video](https://www.youtube.com/watch?v=Z0fQabvVhIk))
* [Nginx Configuration Snippets](https://github.com/lebinh/nginx-conf) — A collection of useful Nginx configuration snippets

## Videos

* [Getting started with Lapis, the web framework](https://www.youtube.com/watch?v=Eo67iTY1Yf8)
* [Building an HTTP request router with NGINX and Lua - Shopify](https://www.youtube.com/watch?v=Cw6Ci9AF23k) (Nginx Conf 2015)
* [Enabling TLS Cross host Session Resumption with Forward Secrecy via ngx lua](https://www.youtube.com/watch?v=JDNJTkDCH0c) (Nginx Conf 2015)
* [The Latest and Greatest from ngx_lua: New Features & Tools](https://www.youtube.com/watch?v=Z0fQabvVhIk) (Nginx Conf 2014)

## Conferences, Workshops and Events

* [OpenResty Con 2016, Shenzen, China](http://con.openresty.org/cn/2016/)
  * New Development of OpenResty in 2016 ([Slides](http://openresty.org/slides/New-development-of-OpenResty-in-2016.pdf), [Video in Chinese](https://youtu.be/H5UFGDaf9Xk))
* [Lua Workshop 2016, San Francisco, USA](http://www.luasf2016.org/) ([Lua.org](https://www.lua.org/wshop16.html))
  * Writing Optimal Lua Code for LuaJIT and OpenResty ([Slides](https://www.lua.org/wshop16/Zhang.pdf), [Video](https://www.youtube.com/watch?v=FfhEdF40nhQ))
* [Bay Area OpenResty Meetup 2016 / 3](http://www.meetup.com/Bay-Area-OpenResty-Meetup/)
  * adobe.io ([Slides](http://openresty.org/slides/adobe-io-openresty-meetup.pdf), [Video](https://www.youtube.com/watch?v=EsLO4aE4TWQ))
  * KONG ([Slides](https://openresty.org/slides/kong_openresty_slides.pdf), [Video](https://www.youtube.com/watch?v=QubcdsDsq_k))
  * What's new in OpenResty for 2016 ([Slides](https://openresty.org/slides/Whats-new-in-OpenResty-for-2016.pdf), [Video](https://www.youtube.com/watch?v=fUGXEkdiqmk))
* [OpenResty Con 2015, Beijing, China](http://www.iresty.com/)
  * The Past, Present, and Future of OpenResty 2015 ([Slides](http://www.iresty.com/download/ebook/2015_con/zhangyichun.pdf), [Video](https://www.youtube.com/watch?v=vUgTHeXM5m8)) (In Chinese)
  * Developing OpenResty Framework ([Slides](http://www.slideshare.net/AapoTalvensaari1/developing-openresty-framework-57404012), [Video](https://www.youtube.com/watch?v=VqBt5icKCI8))
  * Be a Microservice Hero ([Slides](http://www.iresty.com/download/ebook/2015_con/zhangshuai.pdf), [Video](https://www.youtube.com/watch?v=gqRMX8BQD98)) (In Chinese)

## Demo Applications

* [Chat Application presented at OpenResty Conference 2015](https://github.com/bungle/iresty) by [@bungle](https://github.com/bungle)

## See Also

* [awesome-lua](https://github.com/LewisJEllis/awesome-lua) by [@LewisJEllis](https://github.com/LewisJEllis)
* [awesome-lua](https://github.com/forhappy/awesome-lua) by [@forhappy](https://github.com/forhappy)
* [A collection of resources covering Nginx, Nginx + Lua, OpenResty and Tengine](https://github.com/fcambus/nginx-resources)
* [Where Lua is Used](https://sites.google.com/site/marbux/home/where-lua-is-used) and [Lua Uses](http://lua-users.org/wiki/LuaUses)
