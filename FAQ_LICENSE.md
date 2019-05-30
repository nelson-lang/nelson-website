This page should address any licensing concern that anyone may have about using Nelson. We are convinced that Nelson's license allows virtually anyone to use it.

If you still have a concern, don't hesitate to contact us.

The answers below are mutually redundant for the sake of being easier to find.

# General licensing questions

## How is Nelson licensed?

Nelson is dual-licensed: at your choice,

* either under the [![License (GNU Lesser General Public License (LGPL) v2.1)](https://img.shields.io/badge/License-GNU%20Lesser%20General%20Public%20License%20(LGPL)%20v2.1-green.svg?style=flat-square)](https://opensource.org/licenses/LGPL-2.1),
* or under the [![License (GNU General Public License (GPL) v2.0)](https://img.shields.io/badge/license-GNU%20General%20Public%20License%20(GPL)%20v2-blue.svg?style=flat-square)](https://opensource.org/licenses/GPL-2.0).

Note that this is an OR, not an AND. You do not need to conform to both licenses, you just pick the one that you prefer.

Typically, almost everybody will regard Nelson as just LGPL-licensed. 

## What is the LGPL v2.1?
 
The [LGPL v2.1](https://opensource.org/licenses/LGPL-2.1) is one of the most popular open source licenses.

It is quite permissive, at least much more permissive than the GPL license. It allows any software to use Nelson. For example, proprietary software may use Nelson without disclosing any of its own source code.

## So what does the LGPL v2.1 require me to do?

In the following answer, we're assuming that you're using Nelson ''unmodified''. 
If you are using a  ''modified Nelson'', then there's an additional clause.

When you distribute software that ''uses'' Nelson, the LGPL requires you to:
* Say somewhere that that software uses Nelson, and that Nelson is LGPL-licensed.
* Give a link to the text of the [LGPL v2.1](https://opensource.org/licenses/LGPL-2.1) license.
See Section 3 of the[LGPL v2.1](https://opensource.org/licenses/LGPL-2.1).


As long as you're not modifying Nelson's own files, you can safely ignore this. Thus, for almost all of our users, the LGPL is for all practical purposes essentially equivalent to the 2-clause BSD license.


## Why add the GPL v2 as another license choice, since anyway the LGPL v2.1 is more liberal?

There is an circumstance in which the GPL license may be useful. Some optional advanced functionality can be enabled by letting Nelson use external libraries, which we call back-ends. Some such libraries are GPL-licensed. For example, in our FFT module, there is an option to use the FFTW library as a back-end for higher performance. Since FFTW is GPL-licensed, this is only possible if Nelson is used under GPL license. Meanwhile, Users of Nelson can use the Intel MKL back-end and Nelson under LGPL license.

## Using Nelson in proprietary software

 ### Can Nelson be used in proprietary, closed-source software?

This is entirely welcome. Of course, you do not have to disclose any of your own source code. Using Nelson does not affect the licensing of your own software in any way. The LGPL v2.1 license of Nelson does not extend in any way to your own software.

### So is the LGPL v2.1 a perfectly business-friendly license?

LGPL v2.1 is very different from the GPL v2 in this respect. There are countless examples of LGPL-licensed libraries in very wide use by businesses, including in closed-source applications:
* [https://www.qt.io/faq/ Qt], the C++ application framework.
* [http://webkit.org/ WebKit] components such as WebCore and JavaScriptCore, see [http://webkit.org/coding/lgpl-license.html this page].
* [http://ffmpeg.org/legal.html FFmpeg].



## I'm distributing a proprietary, closed-source application that uses Nelson. What am I required to do?

The fact that your application is proprietary does not make any difference here.

## Are there circumstances in which the LGPL v2.1 puts significant other requirements on me?

There is one such circumstance, this is when you are forking Nelson.

As long as you're not modifying Nelson ''itself'', you can safely ignore this. Hence almost all of our users can safely ignore this.


## What about Nelson modules ?

As you may know, Nelson has a module mechanism that can be used to extend it from the outside.

What you have to keep in mind when using the plugins system is that, when you compile your application, typically:
* Nelson is using your plugin
* The code in your plugin is using code from Nelson
* Your application is using the combination (Nelson + your plugin).
It is ''your'' responsibility to pick the right license for your own code so that all of this is possible. If you don't know how to license your module, natural choices to consider are to license it like Nelson, or like your own application (check that the specifics of your case allow it), or under a very permissive license such as MIT or BSD licenses.

[Previous page](README.md)