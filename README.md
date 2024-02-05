# Varnish Docker Container Image

This is a fork of Wodby Varnish with customizations for UMD Libraries environment.

## Docker Images

## Environment Variables

| Variable                                   | Default Value              | Description                                     |
|--------------------------------------------|----------------------------|-------------------------------------------------|
| `VARNISH_ALLOW_UNRESTRICTED_PURGE`         |                            | Used for ban requests as well                   |
| `VARNISH_BACKEND_BETWEEN_BYTES_TIMEOUT`    | `60s`                      |                                                 |
| `VARNISH_BACKEND_CONNECT_TIMEOUT`          | `3.5s`                     |                                                 |
| `VARNISH_BACKEND_FIRST_BYTE_TIMEOUT`       | `60s`                      |                                                 |
| `VARNISH_BACKEND_GRACE`                    | `2m`                       |                                                 |
| `VARNISH_BACKEND_HOST`                     |                            | Mandatory                                       |
| `VARNISH_BACKEND_PORT`                     | `80`                       |                                                 |
| `VARNISH_CACHE_PER_COUNTRY`                |                            | Separate caches based on [country code](#geoip) |
| `VARNISH_CACHE_PER_CURRENCY`               |                            | Separate caches based on [currency](#currency)  |
| `VARNISH_CURRENCY_EUR_COUNTRY_CODES`       |                            | See [currencies](#currency)                     |
| `VARNISH_CURRENCY_USD_COUNTRY_CODES`       |                            | See [currencies](#currency)                     |
| `VARNISH_BIG_FILES_SIZE`                   | `10485760`                 | 10MB                                            |
| `VARNISH_BIG_FILES_TTL`                    | `120s`                     |                                                 |
| `VARNISH_CACHE_STATIC_FILES`               |                            |                                                 |
| `VARNISH_CONFIG_PRESET`                    |                            |                                                 |
| `VARNISH_DEFAULT_TTL`                      | `120s`                     |                                                 |
| `VARNISH_ERRORS_GRACE`                     | `15s`                      |                                                 |
| `VARNISH_PURGE_EXTERNAL_REQUEST_HEADER`    |                            |                                                 |
| `VARNISH_KEEP_ALL_COOKIES`                 |                            |                                                 |
| `VARNISH_KEEP_ALL_PARAMS`                  |                            |                                                 |
| `VARNISH_IMPORT_MODULES`                   |                            | Separated by comma                              |
| `VARNISH_MOBILE_DISABLE_CASH`              |                            |                                                 |
| `VARNISH_MOBILE_SEPARATE_CASH`             |                            |                                                 |
| `VARNISH_MOBILE_USER_AGENT`                |                            | See default value below                         |
| `VARNISH_PIPE_CLOSE_CONNECTION`            |                            |                                                 |
| `VARNISH_PURGE_KEY`                        |                            | Randomly generated if missing                   |
| `VARNISH_SECONDARY_STORAGE_CONDITION`      |                            | Must be valid VCL                               |
| `VARNISH_SECRET`                           |                            | Generated automatically if missing              |
| `VARNISH_STATIC_FILES`                     |                            | See default value below                         |
| `VARNISH_STATIC_TTL`                       | `86400`                    | In seconds                                      |
| `VARNISH_STRIP_COOKIES`                    |                            | See default value below                         |
| `VARNISH_STRIP_PARAMS`                     |                            | See default value below                         |
| `VARNISH_STRIP_ALL_PARAMS`                 |                            | Ignored if `$VARNISH_KEEP_ALL_PARAMS` is set    |
| `VARNISH_PAGESPEED_SECRET_KEY`             |                            | Should be used if mod_pagespeed is enabled      |
| `VARNISHD_DEFAULT_TTL`                     | `120`                      |                                                 |
| `VARNISHD_MEMORY_SIZE`                     | `64m`                      |                                                 |
| `VARNISHD_PARAM_BAN_LURKER_AGE`            | `60.000`                   |                                                 |
| `VARNISHD_PARAM_BAN_LURKER_BATCH`          | `1000`                     |                                                 |
| `VARNISHD_PARAM_BAN_LURKER_SLEEP`          | `0.010`                    |                                                 |
| `VARNISHD_PARAM_BETWEEN_BYTES_TIMEOUT`     | `60.000`                   |                                                 |
| `VARNISHD_PARAM_CONNECT_TIMEOUT`           | `3.500`                    |                                                 |
| `VARNISHD_PARAM_DEFAULT_GRACE`             | `10.000`                   |                                                 |
| `VARNISHD_PARAM_DEFAULT_KEEP`              | `0.000`                    |                                                 |
| `VARNISHD_PARAM_DEFAULT_TTL`               | `120.000`                  |                                                 |
| `VARNISHD_PARAM_FETCH_CHUNKSIZE`           | `16k`                      |                                                 |
| `VARNISHD_PARAM_FIRST_BYTE_TIMEOUT`        | `60.000`                   |                                                 |
| `VARNISHD_PARAM_GZIP_BUFFER`               | `32k`                      |                                                 |
| `VARNISHD_PARAM_GZIP_LEVEL`                | `6`                        |                                                 |
| `VARNISHD_PARAM_GZIP_MEMLEVEL`             | `8`                        |                                                 |
| `VARNISHD_PARAM_HTTP_GZIP_SUPPORT`         | `on`                       |                                                 |
| `VARNISHD_PARAM_HTTP_MAX_HDR`              | `64`                       |                                                 |
| `VARNISHD_PARAM_HTTP_REQ_HDR_LEN`          | `8k`                       |                                                 |
| `VARNISHD_PARAM_HTTP_REQ_SIZE`             | `32k`                      |                                                 |
| `VARNISHD_PARAM_HTTP_RESP_HDR_LEN`         | `8k`                       |                                                 |
| `VARNISHD_PARAM_HTTP_RESP_SIZE`            | `32k`                      |                                                 |
| `VARNISHD_PARAM_IDLE_SEND_TIMEOUT`         | `60.000`                   |                                                 |
| `VARNISHD_PARAM_MAX_ESI_DEPTH`             | `5`                        |                                                 |
| `VARNISHD_PARAM_MAX_RESTARTS`              | `4`                        |                                                 |
| `VARNISHD_PARAM_MAX_RETRIES`               | `4`                        |                                                 |
| `VARNISHD_PARAM_NUKE_LIMIT`                | `50`                       |                                                 |
| `VARNISHD_PARAM_PING_INTERVAL`             | `3`                        |                                                 |
| `VARNISHD_PARAM_PIPE_TIMEOUT`              | `60.000`                   |                                                 |
| `VARNISHD_PARAM_POOL_REQ`                  | `10,100,10`                |                                                 |
| `VARNISHD_PARAM_POOL_SESS`                 | `10,100,10`                |                                                 |
| `VARNISHD_PARAM_PREFER_IPV6`               | `off`                      |                                                 |
| `VARNISHD_PARAM_RUSH_EXPONENT`             | `3`                        |                                                 |
| `VARNISHD_PARAM_SEND_TIMEOUT`              | `600`                      |                                                 |
| `VARNISHD_PARAM_SHORTLIVED`                | `10.000`                   |                                                 |
| `VARNISHD_PARAM_TCP_KEEPALIVE_INTVL`       | `75.000`                   |                                                 |
| `VARNISHD_PARAM_TCP_KEEPALIVE_PROBES`      | `8`                        |                                                 |
| `VARNISHD_PARAM_TCP_KEEPALIVE_TIME`        | `7200.000`                 |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_ADD_DELAY`     | `0.000`                    |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_DESTROY_DELAY` | `1.000`                    |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_FAIL_DELAY`    | `0.200`                    |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_MAX`           | `5000`                     |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_MIN`           | `100`                      |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_STACK`         | `48k`                      |                                                 |
| `VARNISHD_PARAM_THREAD_POOL_TIMEOUT`       | `300.000`                  |                                                 |
| `VARNISHD_PARAM_THREAD_POOLS`              | `2`                        |                                                 |
| `VARNISHD_PARAM_THREAD_QUEUE_LIMIT`        | `20`                       |                                                 |
| `VARNISHD_PARAM_TIMEOUT_IDLE`              | `5.000`                    |                                                 |
| `VARNISHD_PARAM_TIMEOUT_LINGER`            | `0.050`                    |                                                 |
| `VARNISHD_PARAM_VSL_BUFFER`                | `4k`                       |                                                 |
| `VARNISHD_PARAM_VSL_RECLEN`                | `255b`                     |                                                 |
| `VARNISHD_PARAM_VSL_SPACE`                 | `80M`                      |                                                 |
| `VARNISHD_PARAM_VSM_SPACE`                 | `1M`                       |                                                 |
| `VARNISHD_PARAM_WORKSPACE_BACKEND`         | `64k`                      |                                                 |
| `VARNISHD_PARAM_WORKSPACE_CLIENT`          | `64k`                      |                                                 |
| `VARNISHD_PARAM_WORKSPACE_SESSION`         | `0.50k`                    |                                                 |
| `VARNISHD_PARAM_WORKSPACE_THREAD`          | `2k`                       |                                                 |
| `VARNISHD_SECONDARY_STORAGE`               |                            | See example below                               |
| `VARNISHD_SECRET_FILE`                     | `/etc/varnish/secret`      |                                                 |
| `VARNISHD_VCL_SCRIPT`                      | `/etc/varnish/default.vcl` |                                                 |

###### `VARNISH_MOBILE_USER_AGENT`:

###### `VARNISH_STRIP_COOKIES`

## Installed Modules

| Module                                                                                      | Version | Imported |
| ------                                                                                      | ------- | -------- |
| [geoip](https://github.com/varnish/libvmod-geoip)                                           | 1.0.3   | ✓        |
| [digest](https://github.com/varnish/libvmod-digest)                                         | 1.0.2   |          |
| [cookie](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_cookie.rst)       | latest  |          |
| [vsthrottle](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_cookie.rst)   | latest  |          |
| [header](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_header.rst)       | latest  |          |
| [saintmode](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_saintmode.rst) | latest  |          |
| [softpurge](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_softpurge.rst) | latest  |          |
| [tcp](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_tcp.rst)             | latest  |          |
| [var](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_var.rst)             | latest  |          |
| [xkey](https://github.com/varnish/varnish-modules/blob/master/docs/vmod_xkey.rst)           | latest  |          |
| bodyaccess                                                                                  | latest  |          |

