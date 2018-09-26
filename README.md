## R for the motus server ##

This repo tracks the version of R used for the motus server, including
any local changes.

See [here](README) for the upstream R readme.

This version is only meant for the server, and not for use by data
users.

### Upstream Version ###
R-3.4.3

### Build Configuration ###

``` bash
    ./configure --enable-R-shlib --without-x --with-cairo --prefix=/usr
```

### Changelog ###

2018-09-26 protect unsorted list of files to prevent `translateCharUTF8`
           error; see https://bugs.r-project.org/bugzilla/show_bug.cgi?id=17477
           and https://github.com/MotusDev/Motus-TO-DO/issues/230

2018-01-09 allow for much larger headers on http requests to the built-in
           Rhttpd server; otherwise, large cookies, such as those
           generated for modAuthTKT authentication on sgdata.motus.org,
           are breaking header parsing.
           This is contrary to the behaviour described in the code,
           whereby overlong headers are supposed to cause a 413 reply.
