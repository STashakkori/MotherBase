function
--------

Start recording a function for later invocation as a command.

::

  function(<name> [arg1 [arg2 [arg3 ...]]])
    COMMAND1(ARGS ...)
    COMMAND2(ARGS ...)
    ...
  endfunction(<name>)

Define a function named <name> that takes arguments named arg1 arg2
arg3 (...).  Commands listed after function, but before the matching
endfunction, are not invoked until the function is invoked.  When it
is invoked, the commands recorded in the function are first modified
by replacing formal parameters (${arg1}) with the arguments passed,
and then invoked as normal commands.  In addition to referencing the
formal parameters you can reference the variable ARGC which will be
set to the number of arguments passed into the function as well as
ARGV0 ARGV1 ARGV2 ...  which will have the actual values of the
arguments passed in.  This facilitates creating functions with
optional arguments.  Additionally ARGV holds the list of all arguments
given to the function and ARGN holds the list of arguments past the
last expected argument.

A function opens a new scope: see set(var PARENT_SCOPE) for details.

See the cmake_policy() command documentation for the behavior of
policies inside functions.
