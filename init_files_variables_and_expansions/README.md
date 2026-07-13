This is where all the task are executed. Same styling as the other modules.

Current Task Completed(in repo):

| Task | File | What it does |
| --- | --- | --- |
| T0 - Alias | `0-alias` | Creates an alias ls="rm *". |
| T1 - Hello you | `1-hello_you` | Prints hello followed by the current user ($USER). |
| T2 - Path | `2-path` | Adds /action to the end of PATH. |
| T3 - Paths | `3-paths` | Counts how many directories are in PATH. |
| T4 - Global variables | `4-global_variables` | Lists environment variables with printenv. |
| T5 - Local variables | `5-local_variables` | Lists local vars, env vars, and functions with set. |
| T6 - Create local variable | `6-create_local_variable` | Creates local variable BEST="School". |
| T7 - Create global variable | `7-create_global_variable` | Creates global variable BEST="School" with export. |
| T8 - True knowledge | `8-true_knowledge` | Prints TRUEKNOWLEDGE + 128. |
| T9 - Divide and rule | `9-divide_and_rule` | Prints POWER / DIVIDE. |
| T10 - Love exponent breath | `10-love_exponent_breath` | Prints BREATH to the power LOVE. |
| T11 - Binary to decimal | `11-binary_to_decimal` | Converts BINARY from base 2 to base 10. |
| T12 - Combinations | `12-combinations` | Prints all two-letter combos a-z except oo. |
| T13 - Print float | `13-print_float` | Prints NUM with two decimal places. |


Man info for the shell commands

Info of the commands per task (man style):

```
ALIAS / VARIABLES

TASK NOTES
       T0  alias ls="rm *"
           Creates a temporary alias in the current shell when sourced.

       T1  echo "hello $USER"
           $USER expands to the current login name.

       T2  export PATH=$PATH:/action
           Appends /action so it is searched last.

       T3  echo $PATH | tr -s ':' '\n' | wc -l
           Split PATH on : then count lines.

       T4  printenv
           Shows exported environment variables.

       T5  set
           Shows shell variables and functions.

       T6  BEST="School"
           Local variable (not exported).

       T7  export BEST="School"
           Global/environment variable.


ARITHMETIC EXPANSION $(( ))

TASK NOTES
       T8  echo $(($TRUEKNOWLEDGE + 128))
       T9  echo $(($POWER / $DIVIDE))
       T10 echo $(($BREATH**$LOVE))
           ** is exponentiation in bash arithmetic.
       T11 echo $((2#$BINARY))
           2# means interpret BINARY as base 2.


PRINTF / TR / GREP

TASK NOTES
       T12 printf %s\\n {a..z}{a..z}|grep -v oo
           Brace expansion makes aa..zz, grep removes oo.
           Script must stay under 64 characters.

       T13 printf "%.2f\n" $NUM
           Formats NUM with 2 decimal places.
```
