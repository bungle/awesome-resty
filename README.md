# awesome-resty

**awesome-resty** is a curated list of OpenResty of Nginx modules, Lua libraries, and related resources.

**THIS LIST IS CURRENTLY WIP. CONTRIBUTIONS ARE WELCOMED!**

## Libraries

#### Core Libraries

Core Libraries are bundled in OpenResty package, and you don't need to separately install them.

Library|Description
:------|:----------
[lua-resty-core](https://github.com/openresty/lua-resty-core)|New FFI-based Lua API for the ngx_lua module
[lua-resty-string](https://github.com/openresty/lua-resty-string)|String utilities and common hash functions for ngx_lua and LuaJIT
[lua-resty-lock](https://github.com/openresty/lua-resty-lock)|Simple nonblocking lock API for ngx_lua based on shared memory dictionaries
[lua-resty-lrucache](https://github.com/openresty/lua-resty-lrucache)|Lua-land LRU Cache based on LuaJIT FFI
[lua-resty-dns](https://github.com/openresty/lua-resty-dns)|DNS resolver for the Nginx Lua module
[lua-resty-upload](https://github.com/openresty/lua-resty-upload)|Streaming reader and parser for HTTP file uploading based on ngx_lua cosocket
[lua-resty-websocket](https://github.com/openresty/lua-resty-websocket)|Lua WebSocket implementation for the ngx_lua module
[lua-resty-memcached](https://github.com/openresty/lua-resty-memcached)|Lua memcached client driver for the ngx_lua based on the cosocket API
[lua-resty-redis](https://github.com/openresty/lua-resty-redis)|Lua Redis client driver for the ngx_lua based on the cosocket API
[lua-resty-mysql](https://github.com/openresty/lua-resty-mysql)|Non-blocking Lua MySQL client driver for ngx_lua based on the cosocket API
[lua-resty-upstream-healthcheck](https://github.com/openresty/lua-resty-upstream-healthcheck)|Health Checker for Nginx Upstream Servers in Pure Lua

#### Cryptography
#### Networking
#### Databases and Storages

## Books and Tutorials

#### Tutorials and Guides

* [agentzh's Nginx Tutorials](http://openresty.org/download/agentzh-nginx-tutorials-en.html)

