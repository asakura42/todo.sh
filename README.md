# todo.sh
simpler and faster that Gina's bloat. 42 SLOC.

Added to vanilla todo.txt idea:

1. `due:` to set due date
2. `!` after priority for pin task

So it becomes (colored):

```sh
!       (F)     walk              @city               2021-07-25
        (C)     buy milk          @food     +home     2021-07-17
                listen to music             +random  
```
By default list is sorted by:

1. Pin
2. Due date
3. Priority

Any `"$@"` will be interpreted as query for grep function
