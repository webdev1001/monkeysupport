#MonkeySupport#

MonkeySupport is a collection of monkeypatches to Rails, replacing
existing methods with (somewhat) optimized C equivalents.

If this interests you, you should also check out methodmissing's
excellent HashWithIndifferentAccess at
http://github.com/methodmissing/hwia .

##Modules##

MonkeySupport is largely a bunch of modules, each overwriting a part
of ActiveSupport. By setting `$MonkeyModuleExcludes` to an array of
module names before loading MonkeySupport, those modules will not be
loaded. For example:

    $MonkeyModuleExcludes = ["inflector", "output_safety"]
    require 'monkeysupport'

MonkeySupport is currently comprised of the following modules:

* inflector
* output_safety

##Note on Patches/Pull Requests##
 
* Fork the project.
* Make your feature addition or bug fix.
* Add tests for it. This is important so I don't break it in a
  future version unintentionally.
* Commit, do not mess with rakefile, version, or history.
  (if you want to have your own version, that is fine but
   bump version in a commit by itself I can ignore when I pull)
* Send me a pull request. Bonus points for topic branches.

##Problems / TODO##

* I haven't figured out a simple way to get this running with the
  rails test suite. That would be handy.
* Certain functions are memoized now, that rails doesn't memoize by
  default. I've tried to choose carefully, but with unusual usage
  patterns, this could cause memory issues. Simplest solution that
  comes to my mind would be to use a simple LRU cache instead of a
  plain hash.
* There's always more to port...

##Copyright##

Copyright (c) 2009 Burke Libbey. MIT License. See LICENSE for details.