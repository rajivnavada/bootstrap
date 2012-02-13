NOTE
====

This repo does not add any new functionality to the original <a href="https://github.com/twitter/bootstrap">Twitter Bootstrap</a> repo. The only change is to the `Makefile` which adds a `proper` target that may be used for generating js files that work well as embeddable components.

The Problem
-----------

The maintainer of the original repository is apparently adamant about not using semicolons EVER! Of course this is not a problem when you use `uglify-js` to build the concatenated bootstrap.js file. If you are happy with that solution, there is nothing in this repo that has changed.

The problem with using the concatenated file is that you have to load all the js components even if all you need is one plugin. If you concatenate any individual plugin file with your own file and load it up in the browser without running the concatenation through `uglify` (for example: during development), it is highly likely that the browser throws an error saying something along the lines of `undefined is not a function`. This happens due to a missing semicolon that denotes the end of the plugin.

Usage
-----

* `make proper` to add the missing semicolons to the end of each plugin file.
* All other options to `make` remain unchanged.


Copyright and license
---------------------

Copyright 2012 Twitter, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this work except in compliance with the License.
You may obtain a copy of the License in the LICENSE file, or at:

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
