---
title: meck
layout: default
---

<div class="download">
     <a href="http://github.com/eproxus/meck/zipball/master">
        <img border="0" width="90" src="http://github.com/images/modules/download/zip.png"></a>
     <a href="http://github.com/eproxus/meck/tarball/master">
        <img border="0" width="90" src="http://github.com/images/modules/download/tar.png"></a>
</div>

meck
==================================

*A mocking library for Erlang*

With meck you can easily mock modules in Erlang. Since meck is intended to be used in testing, you can also perform some basic validations on the mocked modules, such as making sure no function is called in a way it should not.

meck automatically renames existing modules in case they are loaded when you want to mock them, and restores them upon unloading of the mocked module. It is also possible to call the original functions from a mocked module using `meck:passthrough/1` from inside an expectation.

Example
-------

Here's an example of using meck in the Erlang shell:

{% highlight erlang %}
Eshell V5.7.5  (abort with ^G)
1> meck:new(dog).
ok
2> meck:expect(dog, bark, fun() -> "Woof!" end).
ok
3> dog:bark().
"Woof!"
4> meck:validate(dog).
true
{% endhighlight %}

Download
--------

You can download this project in either [zip][1] or [tar][2] formats.

You can also clone the project with [Git][3] by running this in a unix shell:

    git clone git://github.com/eproxus/meck


Build and Install
-------

To build meck and run the tests, simply type:

    ./rebar eunit

To install meck, put it in your project directory where your Erlang applications are located and make sure that the load path to the `meck/ebin` folder is set up correctly (if you want to run from the shell, do `code:add_patha("/path/to/meck/ebin")`). For more instructions, see [Build and Install][4] on the meck wiki.

Happy hacking!

Feedback
--------

Please create and vote for issues at the [issue tracker for meck][5].

[1]: http://github.com/eproxus/meck/zipball/master "Zip file containing the latest version of meck"
[2]: http://github.com/eproxus/meck/tarball/master "Tar file containing the latest version of meck"
[3]: http://git-scm.com/ "Git, the fast version control system"
[4]: http://wiki.github.com/eproxus/meck/build-and-install "How to build and install meck"
[5]: http://github.com/eproxus/meck/issues "meck issue tracker on Github"
