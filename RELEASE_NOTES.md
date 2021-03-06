## v2.11.0

* Various fixes and clarifications.
* Change implementation of available_network_names to use REXML; first implemented w/position number, then XPath.
* Add attempt count to try_os_command_until in verbose mode.

## v2.10.1

* Fix egregious bug; the 'a' command did not work if `airport` was not in the path; I should have been using the AIRPORT_CMD constant but hard coded `airport` instead.

## v2.10.0

* Rename rm[_pref_nets] command to f[orget].
 

## v2.9.0

* Add duration of command to verbose output.
* Add MAC address to info hash.
* Reduce ping timeout to 3 seconds for faster return for `info`, `ci` commands.
* Replace ipchicken.com link with iplocation.net link for 'ropen'; iplocation aggregates several info sources.
* Fix bug where if there were no duplicate network names, result was nil, because uniq! returns nil if no changes!!!
* Suppress error throw on ping error when not connected; it was printing useless output.

## v2.8.0

* Substantial simplifications of model implementations of connected_to_internet?, available_network_names.
* Fixed network name reporting problems regarding leading/trailing spaces.
* Improve verbose output by printing command when issued, not after completed.


## v2.7.0

* Fix models not being loadable after requiring the gem.
* Add message suggesting to gem install awesome_print to help text if not installed.
* Add Github project page URL to help text.
* Rename 'wifion' to 'wifi_on'.
* Change order of verbose output and error raising in run_os_commmand.


## v2.6.0

* Add support for getting and setting DNS nameservers with 'na'/'nameservers' command.
* Improve error output readability for top level error catching.


## v2.5.0

* Add limited support for nonstandard wifi devices (https://github.com/keithrbennett/wifiwand/issues/6).


## v2.4.2

* Fix test.


## v2.4.1

* Fix bug: undefined local variable or method `connected_network_name'.


## v2.4.0

* Project has been renamed from 'mac-wifi' to 'wifi-wand'.
* Further preparation for addition of support of other OS's.
* Make resource opening OS-dependent as it should be.
* Move models to models directory.
* Refactored OS determination and model creation.
* Use scutil --dns to get nameserver info, using the union of the scoped and unscoped nameservers.


## v2.3.0

* Add public IP address info to info hash (https://github.com/keithrbennett/macwifi/issues/3).
* Add nameserver information to info hash (issue at https://github.com/keithrbennett/macwifi/issues/5).
* Made all info hash keys same data type to be less confusing; made them all String's.
* Replace 'public-ip-show' with 'ropen', and provide additional targets ipchicken.com,
 speedtest.net, and the Github page for this project
* Speed up retrieval of network name
* Remove BaseModel#run_os_command private restriction.


## v2.2.0

* Add pu[blic-wifi-show] command to open https://www.whatismyip.com/ to show public IP address info.
* Removed 'vpn on' info from info hash; it was often inaccurate.


## v2.1.0

* Support for the single script file install has been dropped. It was requiring too much complexity,
and was problematic with Ruby implementations lacking GEM_HOME / GEM_PATH environment variables.
* Code was broken out of the single script file into class files, plus a `version.rb`
and `mac-wifi.rb` file.


## v2.0.0

* Support output formats in batch mode: JSON, YAML, puts, and inspect modes.
* Change some command names to include underscores.
* Shell mode is now (only) a command line switch (-s).


## v1.4.0

* Support for "MAC-WIFI-OPTS" environment variable for configuration dropped.
* Support for "-v" verbosity command line option added.
* Work around pry bug whereby shell was not always starting when requested.
* 99% fix for reporting of available network names containing leading spaces
  (this will not correctly handle the case of network names that are identical
  except for numbers of leading spaces).
* Improved handling of attempting to list available networks when wifi is off.


## v1.3.0

* Add partial JSON and YAML support.
* Script moved from bin to exe directory.
* Provide `fp` fancy print alias for convenience in shell.
* Command renames: 'lsp' -> 'prefnets', 'rm' -> 'rmprefnets'
* Add 'availnets' command for list of unique available network names.


## v1.2.0

* Fix: protect against using command strings shorter than minimum length
      (e.g. 'c', when more chars are necessary to disambiguate multiple commands).
* Improvements in help text and readme.


## v1.1.0

* Sort available networks alphabetically, left justify ssid's.
* to_s is called on parameters so that symbols can be specified in interactive shell for easier typing


## v1.0.0

* First versioned release.



