# awesome-resty

**awesome-resty** is a curated list of OpenResty of Nginx modules, Lua libraries, and related resources.

**THIS LIST IS CURRENTLY WIP. CONTRIBUTIONS ARE WELCOMED!**

## Official Channels

* Web Site: http://openresty.org/
* Mailing List: https://groups.google.com/forum/#!forum/openresty-en
* Github Organization: https://github.com/openresty
* Lead Developer: [@agentzh](https://github.com/agentzh)

## Modules

#### Core Modules

Module|Description
:-----|:----------
[ngx_openresty](https://github.com/openresty/ngx_openresty)|Turning Nginx into a full-fledged Web App Server - Sources for OpenResty Bundle Generation
[lua-nginx-module](https://github.com/openresty/lua-nginx-module)|Embed the power of Lua into Nginx - **The single most important part of OpenResty**

## Libraries

#### Core Libraries

Core Libraries are bundled in OpenResty package, and you don't need to separately install them.

Library|Description
:------|:----------
[lua-resty-core](https://github.com/openresty/lua-resty-core)|New FFI-based Lua API for the ngx_lua module
[lua-resty-upstream-healthcheck](https://github.com/openresty/lua-resty-upstream-healthcheck)|Health Checker for Nginx Upstream Servers in Pure Lua
[lua-resty-string](https://github.com/openresty/lua-resty-string)|String utilities and common hash functions for ngx_lua and LuaJIT
[lua-resty-lock](https://github.com/openresty/lua-resty-lock)|Simple nonblocking lock API for ngx_lua based on shared memory dictionaries
[lua-resty-lrucache](https://github.com/openresty/lua-resty-lrucache)|Lua-land LRU Cache based on LuaJIT FFI
[lua-resty-dns](https://github.com/openresty/lua-resty-dns)|DNS resolver for the Nginx Lua module
[lua-resty-upload](https://github.com/openresty/lua-resty-upload)|Streaming reader and parser for HTTP file uploading based on ngx_lua cosocket
[lua-resty-websocket](https://github.com/openresty/lua-resty-websocket)|Lua WebSocket implementation for the ngx_lua module
[lua-resty-mysql](https://github.com/openresty/lua-resty-mysql)|Non-blocking Lua MySQL client driver for ngx_lua based on the cosocket API
[lua-resty-memcached](https://github.com/openresty/lua-resty-memcached)|Lua memcached client driver for the ngx_lua based on the cosocket API
[lua-resty-redis](https://github.com/openresty/lua-resty-redis)|Lua Redis client driver for the ngx_lua based on the cosocket API
[lua-redis-parser](https://github.com/openresty/lua-redis-parser)|Redis reply parser and request constructor library for Lua
[lua-rds-parser](https://github.com/openresty/lua-rds-parser)|Resty-DBD-Stream (RDS) parser for Lua written in C
[lua-cjson](https://github.com/openresty/lua-cjson)|Lua cJSON is a fast JSON encoding / parsing module for Lua

#### Frameworks

Framework|Description
:--------|:----------
[Lapis](http://leafo.net/lapis/)|Lapis is a framework for building web applications using MoonScript or Lua that runs inside of a customized version of Nginx called OpenResty


#### Templating

Library|Description
:------|:----------
[lua-resty-template](https://github.com/bungle/lua-resty-template)|A Compiling (HTML) templating engine for Lua and OpenResty
[etlua](https://github.com/leafo/etlua)|Embedded Lua templates

#### Cryptography

Library|Description
:------|:----------
[lua-resty-string](https://github.com/openresty/lua-resty-string)|String utilities and common hash functions for ngx_lua and LuaJIT
[lua-resty-nettle](https://github.com/bungle/lua-resty-nettle)|LuaJIT FFI bindings for Nettle (a low-level cryptographic library)

#### Networking

Library|Description
:------|:----------
[lua-resty-http](https://github.com/pintsized/lua-resty-http)|Lua HTTP client cosocket driver for OpenResty / ngx_lua
[lua-resty-http](https://github.com/liseen/lua-resty-http)|Lua http client driver for the ngx_lua based on the cosocket API
[lua-resty-http-simple](https://github.com/bakins/lua-resty-http-simple)|Simple Lua HTTP client driver for ngx_lua
[lua-resty-httpclient](https://github.com/oneoo/lua-resty-httpclient)|Nonblocking Lua HTTP Client library for aLiLua & ngx_lua
[lua-httpcli-resty](https://github.com/mah0x211/lua-httpcli-resty)|Lua HTTP client module for OpenResty

#### Databases and Storages

Library|Description
:------|:----------
[lua-resty-mysql](https://github.com/openresty/lua-resty-mysql)|Non-blocking Lua MySQL client driver for ngx_lua based on the cosocket API
[pgmoon](https://github.com/leafo/pgmoon)|A pure Lua Postgres driver for use in OpenResy & more
[lua-resty-memcached](https://github.com/openresty/lua-resty-memcached)|Lua memcached client driver for the ngx_lua based on the cosocket API
[lua-resty-redis](https://github.com/openresty/lua-resty-redis)|Lua Redis client driver for the ngx_lua based on the cosocket API
[lua-resty-cassandra](https://github.com/jbochi/lua-resty-cassandra)|Pure Lua Cassandra client using CQL binary protocol
[lua-resty-riak](https://github.com/bakins/lua-resty-riak)|Lua riak protocol buffer client driver for the ngx_lua based on the cosocket API
[lua-resty-mongo](https://github.com/nightsailer/lua-resty-mongo)|Lua mongodb client driver for the ngx_lua based on the cosocket API
[lua-resty-ssdb](https://github.com/LazyZhu/lua-resty-ssdb)|Lua ssdb client driver for the ngx_lua based on the cosocket API, SSDB is a leveldb server
[lua-resty-fastdfs](https://github.com/azurewang/lua-resty-fastdfs)|Nonblocking Lua FastDFS driver library for ngx_lua

#### Message Queuing, and Task Management

Library|Description
:------|:----------
[lua-resty-rabbitmqstomp](https://github.com/wingify/lua-resty-rabbitmqstomp)|Lua RabbitMQ client library which uses cosocket api for communication over STOMP 1.2 with a RabbitMQ broker which has the STOMP plugin
[lua-resty-gearman](https://github.com/zhhchen/lua-resty-gearman)|Lua gearman client driver for the ngx_lua based on the cosocket API
[lua-resty-kafka](https://github.com/doujiang24/lua-resty-kafka)|Lua kafka client driver for the ngx_lua based on the cosocket API

#### Web APIs

Library|Description
:------|:----------
[lua-resty-github](https://github.com/jamesmarlowe/lua-resty-github)|Lua library for using the github api in the ngx_lua nginx module
[lua-resty-hipchat](https://github.com/jamesmarlowe/lua-resty-hipchat)|Lua library for using the hipchat api
[lua-resty-aws](https://github.com/grosskur/lua-resty-aws)|AWS signature V4 library for OpenResty + Lua

## Books and Tutorials

#### Tutorials and Guides

* [agentzh's Nginx Tutorials](http://openresty.org/download/agentzh-nginx-tutorials-en.html)

## See Also

* [A collection of resources covering Nginx, Nginx + Lua, OpenResty and Tengine](https://github.com/fcambus/nginx-resources)
