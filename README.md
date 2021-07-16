# todo.sh
## simpler and faster than Gina's bloat. 27 SLOC.

Added to vanilla todo.txt idea:

1. `due:` to set due date
2. `!` after priority for pin task

So it becomes (colored):

```sh
!       (F)     walk              @city               2021-07-25
        (C)     buy milk          @food     +home     2021-07-17
                listen to music             +random  
```

Colors like in official todotxt-cli (yellow for A, green for B, blue for C). **Added red for tasks with expired due.**

By default list is sorted by:

1. Pin
2. Due date
3. Priority

Any `"$@"` will be interpreted as query for grep function


### Examples

`todo $(date +%F)`: outputs today's tasks  
`todo | awk '$NF ~ /2/'`: tasks with date  
`todo | awk '$NF !~ /2/'`: tasks without date

#### inotify example:  
```sh
todo && while inotifywait -qq ~/todo.txt ; do
        t=$(todo);clear;echo "$t"
done
```

### TODO
1. Daemon mode and alarms at specified hours
2. Recurrent tasks
3. Master/slave tasks
4. Keeping it simple stupid
