lesser-parallel
===============

Lesser Parallel, a bash script library like the [GNU Parallel](http://www.gnu.org/software/parallel/).
It only has lesser functions than the GNU Parallel. But it can use easily in any bash script by embedding.

Usage
=====

    Usage:
      lesser-parallel [<options>] [<command> [<arguments> ...]] < <list_to_arguments>
      cat ... | lesser-parallel [<options>] [<command> [<arguments> ...]]
    Options:
      -j <n>      : Run <n> jobs in parallel.
      -e [<file>] : Embed Lesser Parallel to <file>.
      -h, --help  : Display help and ext.
    Arguments:
      Each jobs receive input line from STDIN into placeholders.
      Placeholders will be substituted with input line as below:
      {}   : Input line.
      {.}  : Input line without extention (pathname).
      {/}  : Input line without directory (basename).
      {//} : Input line without basename (dirname).
      {/.} : Input line without directory and extension (basename without suffix).
      {#}  : Job sequence number of paralell.

`-e` option embed a part of this script into FILE between the begin marker (`# Lesser Parallel for Embedding`) and the end marker (`#/Lesser Parallel for Embedding`).

The environment variable `LESSER_PARALLEL_MAX_JOBS` defines number of jobs to run up in parallel.

License
=======
[The MIT license](LICENSE).