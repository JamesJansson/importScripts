EpiML
=====
Use javascript libraries in node.js
importScripts is not defined in node.js. This can be annoying if you want to use standard JS libraries in global scope.

In particular, a library that drops lots of useful functions into global scope may not have a node.js maintained equivalent

Usage
=====
importScripts
Use this method if you want to address the library as it were a file local to a webworker. Execution path is relative to where node.js is executed from
importScripts=require('importScripts').importScripts;
importScripts('library.js')

include
Use this method if you want to address the library from an arbitrary location
include=require('importScripts').include;

FAQ?
You're just polluting the global space!!!

That's not a question, but thanks for asking. Sometimes there are great javascript libraries that we just want to use, without having to convert it to node.js exports format. Remember that the global scope belongs to the person who is using it. If they want to load it into global scope, they should be able to. More importantly, they should be able to drop libraries into a module's scope. 