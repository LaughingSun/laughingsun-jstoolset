# xhrloader-factory
a javascript/ecmascript xhrloader with caching. plugin and factory features, built for speed first and flexibility second.

Installation Summary
====================

Node:

    > npm xhrloader-factory
    
    or
    
    > npm xhrloader-factory -g
    
wget:

  > wget https://github.com/LaughingSun/tools/xhrloader-factory/build/xhrloader-factory.min.js
    


Initialization Summary
======================

for Node:

  var XHRLoad = require('./xhrloader-factory')

for AMD:

  define(['xhrloader-factory'], function () {
    /* your code here */
  });

   
for Browser

  <script src="xhrloader-factory.js"></script>
  
Usage Summary
=============

loader as XHRLoader:
  + loader as function: loader(path:{string!}, callback:{function!}, conf:{object?}):loader
  + loader as constructor: new loader(conf:{object?}):{function /* new XHRLoader */}
  + #factory method: loader.factory(conf:{object?}):{function /* new XHRLoader */}
  + #load method: loader.load(path:{string!}, callback:{function!}, conf:{object?}):{#}
  + #abort method: loader.abort(path:{string?}, callback:{function?}):{#}
  + #test method: loader.test(path:{string!}, headers:{object?}):{XMLHttpRequest{#} | null}
  + #removeFromCache method: loader.removeFromCache(path:{string!}}, conf:{object?}):{#}
  + #normalizePath method: loader.normalizePath(path:{string!}}):{string}
  + #cache property(getter): loader.cache:{object}
  + #isComplete property(getter): loader.isComplete:{boolean}
  + #onComplete property(getter/setter): loader.onComplete:{function | null}

XHRLoader argument descriptions:
  + path:{string}:
      - a url and a key for the cache
  + callback:{function(err:{error | null}, content:{any?}, type:{string?}, progress:{number?}, retryCounter:{number?})}
      - the xhr callback used on all xhr events
  * conf:{object}
      - using the following useful properties, other are ignored:
        + cache:{object | false}
        + timeout:{number}
        + maxRetries:{number}
        + retryDelay:{number | array}
        + onComplete:{function(err:{error | null})}
  
  
