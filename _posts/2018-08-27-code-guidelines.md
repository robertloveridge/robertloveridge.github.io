---
layout: post
title:  "Code guidelines"
date:   2018-08-27
categories: development
---

Here are some basic code guidelines I _try to use_ for development. There will of course be a set of best practices for the language you're using, for example, Perl Best Practices is a good place to start but listed below are some good notes.

## General

 * Split up code into logical pieces as much as is sensible
 * Write your classes with a view to testing them
 * Code for maintainability, reusability and clarity over performance

## Coding style

 * Indent with (4 character) tabs
 * Try to stick to 76-80 character lines. Doing that forces you to think twice before embedding huge strings and indecipherable chained method calls
 * Don't write massive indecipherable assignments in one wall of code
 * It's okay to `return undef`. Using a bare `return;` breaks horribly if you're trying to assign the result to a hash
 * `unless` is okay. Only positive conditions, though (i.e, `unless ($foo && !$bar)` is way too confusing, don't do it), and no `else` blocks with `unless`!
 * Use OO by default (ideally via Moose) as it helps with code reuse and keeps everything using a predictable interface

## When writing scripts

Try not to lock up functionality in a script. Code in scripts isn't easily reusable elsewhere. Use a separate module to provide the functionality and have the script simply implement the interface.

## Basic tests

### The compile-only switch

A simple way to check the syntax of a script and output any potential problems is with this switch. Perl will run a syntax check on your file.

```
perl -c /path/to/script.pl
```

> It doesn't *just* run a syntax check!

Thanks to BEGIN blocks, some Perl code may be executed during a theoretically safe "syntax check". For example, if your code was:

```perl
BEGIN { system "rm", "-rf", "/" }
```

This could be dangerous, especially if you only consider it a "compile only". The above would wipe your disk, even though you thought it was safe!

### Test the POD

You can test all of the POD on all modules with this one line command. It will let you know if a module has no pod or if there are errors.

```
perl -I lib/ -e "use Test::Pod; all_pod_files_ok(all_pod_files( 'lib/Your/Path/' ));"
```

## Final thoughts

When you're working in a team, it helps if you all stick to a common style but you shouldn't be afraid to point out inefficiencies in other people's code.

Don't be afraid to hack away at other people's code if it needs work (but try not to break it).
