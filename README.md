JReadability
============

Author: David Wu <david@wu-man.com> <http://blog.wu-man.com>


ABOUT
-----

JReadability is a Java library that parses HTML as input and returns clean,
easy-to-read text.

JReadability is a Java port of [arc90](http://arc90.com/)'s original 
Javascript project [Readability](http://code.google.com/p/arc90labs-readability/).
(The original Readability.js project is now migrated to become a server-side
platform which as far as I know is no longer open source.)


EXAMPLES
--------

Instantiate the `Readability` class via any one of the provided constructors,
depending on where the interested HTML page is from:

    Readability readability = new Readability(html); // String
    Readability readability = new Readability(url, timeoutMillis);  // URL

Start content extraction by running:

    readability.init();

The output is clean, readable content in HTML format.  You can obtain the
output with:

    String cleanHtml = readability.outerHtml();

By default debug logs are printed using `System.out.println()`.  You may
alternatively use your own logging mechanisms by overriding the `dbg()` 
methods.  For instance, on Android you may choose to do this:

    Readability readability = new Readability(html) {
        @Override
        protected void dbg(String msg) {
            Log.d(LOG_TAG, msg);
        }

        @Override
        protected void dbg(String msg, Throwable t) {
            Log.e(LOG_TAG, msg, t);
        }
    };


INCLUDING IN YOUR PROJECT
-------------------------

There are two ways to include JReadability in your projects:

1. You can download the released jar file in the [Downloads section](https://github.com/wuman/JReadability/downloads).
2. If you use Maven to build your project you can simply add a dependency to this library.

        <dependency>
            <groupId>com.wu-man</groupId>
            <artifactId>jreadability</artifactId>
            <version>1.3</version>
        </dependency>


DEPENDENCY
----------

JReadability depends on the [jsoup](https://github.com/jhy/jsoup/) library.


REFERENCE
---------

+ [blog post](http://blog.wu-man.com/2012/10/introducing-jreadability-making-web.html)
+ arc90's [readability project](http://code.google.com/p/arc90labs-readability/)
+ fivefilters [php-readability](http://code.fivefilters.org/php-readability)
+ jhy's [jsoup](https://github.com/jhy/jsoup/) parser


CONTRIBUTE
----------

If you would like to contribute code to JReadability you can do so through 
GitHub by forking the repository and sending a pull request.


LICENSE
-------

    Copyright 2012 David Wu

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software 
    distributed under the License is distributed on an "AS IS" BASIS, 
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and 
    limitations under the License.

