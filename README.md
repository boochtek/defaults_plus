defaults_plus
=============

This is a knock-off of the Mac OS X `defaults` program, but able to manipulate nested dicts.


Usage Examples
--------------

To get all the settings for the **Basic** profile in Terminal:

~~~ shell
defaults+ read com.apple.Terminal 'Window Settings.Basic'
~~~

To add a setting to that profile (to disable the audible bell feature):

~~~ shell
defaults+ write com.apple.Terminal 'Window Settings.Basic.Bell' 0
~~~

To read the setting you just wrote:

~~~ shell
defaults+ read com.apple.Terminal 'Window Settings.Basic.Bell'
~~~

To copy one Terminal profile to another:

~~~ shell
defaults+ copy com.apple.Terminal 'Window Settings.Basic' 'Window Settings.Copy of Basic'
defaults+ write com.apple.Terminal 'Window Settings.Copy of Basic.name' 'Copy of Basic'
~~~



TODO
----

* Add `delete` command.
* Add `rename` command.
* Add other types of items for `write`.
  * data
  * bool, float, etc.
  * array, dict
  * array-add, dict-add
  * with and without flag explicitly specifying type
* Add `read-type` command.
* Require a flag to overwrite an array or hash with a single value.
* Handle the case where an intermediate key doesn't exist.
* Accept `-app Terminal` syntax for the domain.
* Accept the same `<value_rep>` syntax that `defaults` does.
* Allow specifying the key path separator.
* Do real command-line option parsing and help.


Copyright
---------

Copyright (c) 2014 Craig Buchek  
Copyright (c) 2014 BoochTek, LLC

This software is licensed under the terms of the MIT License. See [LICENSE.txt] for details.

[LICENSE.txt]: LICENSE.txt


Contributing
------------

1. Fork it.
2. Create your feature branch (`git checkout -b my-new-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin my-new-feature`).
5. Create new Pull Request.
