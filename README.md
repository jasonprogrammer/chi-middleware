# Chi-Middleware (Logging changes)

This is a fork of the [chi middleware](https://github.com/go-chi/chi/tree/master/middleware) that changes the default logging functionality to do the following:

1. Output logs according to the [Combined Log Format](https://httpd.apache.org/docs/1.3/logs.html#combined). This makes it easy to use a log file analyzer, like [GoAccess](https://goaccess.io/) to visualize your web visitors.

2. Rotate log files using the [Lumberjack](https://github.com/natefinch/lumberjack) library.

## Usage

The usage of this module is similar to the other Chi middleware:

```
import (
    "github.com/jasonprogrammer/chi-middleware"
)

//optionally override the logging path
middleware.DefaultLogger = middleware.GetDefaultRequestLogger(
    "/var/log/mywebsite/access.log"
)

r.Use(middleware.Logger)
```
