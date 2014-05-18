lesser-parallel
===============

Lesser Parallel, a bash script library like the [GNU Parallel](http://www.gnu.org/software/parallel/).
It only has lesser functions than the GNU Parallel. But it can use easily in any bash script with embedding.

Usage
=====

    Usage:
      lesser-parallel [options] [command [arguments]] < list_ot_arguments
      cat ... | lesser-parallel [options] [command [arguments]]
    options:
      -j N        Run n jobs in parallel
      -e [FILE]   Embed Lesser Parallel to FILE
      -h, --help
    arguments:
      {} {.} {/} {/.} {#}  Replacement strings

`-e` option embed a part of this script into FILE between the begin marker (`# Lesser Parallel for Embedding`) and the end marker (`#/Lesser Parallel for Embedding`).

The environment variable `LESSER_PARALLEL_MAX_JOBS` defines number of jobs to run up in parallel.
