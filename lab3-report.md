# Lab 3 Report
# The `grep` Command

## Introduction
The `grep` command is useful for searching directories and files for various text patterns.
These are four different command-line options along with two examples of using each option within the `./written_2` directory.

## Using `-r` option
The `-r` parameter is often used when you want to search many files contained within a folder structure.
This is necessary for recursively searching the entire directory and printing the text that contains the string.
Here are two examples of the `r` option in use with written_2 as the current working directory:
1. The first example displays text found that contains "Houston". Oddly, we observe the `California-WhereToGo.txt` file is returned despite Houston being located in Texas.
~~~
$ grep -r "Houston"
written_2/non-fiction/OUP/Castro/chB.txt:my Quinto of Houston
written_2/travel_guides/berlitz2/California-WhereToGo.txt:The town is proud of its past and offers a self-guided tour of all the Old Town’s historic 19th-century buildings. Look out for the Larkin House, at Jefferson and Calle Principal, home of the first (and only) United States Consul in the 1840s, as well as the Stevenson House, 530 Houston Street, where the Scottish writer Robert Louis Stevenson lived for four months after his arrival in California in 1879. Some think that the nearby coastline around Point Lobos provided the inspiration for the setting of his famous adventure novel, Treasure Island.
~~~
2. The second example demonstrates how more specific strings can return desirable results. In this case, you may want to find a beach for swimming and sunning and Vallarta meets that criteria!
~~~
$ grep -r "beach for swimming and sunning"
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:A boat ride away from Vallarta, Yelapa offers a Robinson Crusoe–style getaway for day trips or overnight stays. No electricity and no roads 
keep it a secluded, funky beach community, populated in part by ex-pats and artists. The other south shore beaches are Las Animas and Quimixto, appropriate for day trips only. These two offer palapa beach dining, and as tropical a setting as you can dream up. Las Animas has the better beach for swimming and sunning, but Quimixto has a beautiful waterfall that you can reach by walking about 30 minutes inland along a well-marked trail. The coves surrounding Quimixto are also noted by divers and snorkelers for their excellent underwater vistas. These three beaches may all be reached by excursion boat, or for longer, less structured stays, take the water taxi from either the Rosita (malecón) , or Los Muertos pier.
~~~

## Using `-c` option
The `-c` option is particularly useful when you want to suppress the `grep` output and receive a count of the occurences a pattern appears within a file.
1. This is one example of how it may be used to find the number of lines within IntroLasVegas.txt contain "desert":
~~~
$ grep -c "desert" IntroLasVegas.txt
5
~~~
2. If we don't want as much specificity in where we want to search more than a single file, `-r` can be used concurrently to search the entire structure as well as opposed to a single file:
~~~
$ grep -rc "desert"
...
written_2/travel_guides/berlitz2/PuertoRico-History.txt:0
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt:1
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:1
written_2/travel_guides/berlitz2/Vallarta-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:2
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:2
~~~
## Using `-E` option
The `-E` option is used to search for multiple patterns with regular expression.
1. Here is an example of how `-E` can be used to search written_2 in combination with `-r` and `-c`:
~~~
$ grep -rcE "sand|beach"
...
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt:46
written_2/travel_guides/berlitz2/PuertoRico-History.txt:1
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt:4
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:25
written_2/travel_guides/berlitz2/Vallarta-History.txt:6
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:17
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:63
~~~
This would be useful if someone is trying to find places that have sand OR beaches using the `|` operand.
2. This is another example that someone could use if they're interested in finding locations with an emphasis on food:
~~~
...
$ grep -rcE "cuisine|food|restaurant"
written_2/travel_guides/berlitz1/HandRIsrael.txt:42
written_2/travel_guides/berlitz1/HandRIstanbul.txt:0
written_2/travel_guides/berlitz1/HandRJamaica.txt:35
written_2/travel_guides/berlitz1/HandRJerusalem.txt:1
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt:0
written_2/travel_guides/berlitz1/HandRLasVegas.txt:0
written_2/travel_guides/berlitz1/HandRLisbon.txt:1
...
~~~

## Using `-i` option
Oftentimes, the return of `grep` may not be fully inclusive, but using `-i` allows for a case-insensitive search.
1. This is an example of using `i` to find a text file that contains "local cuisine" regardless of case:
~~~
$ grep -ril "local cuisine"
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt
~~~

2. Here, the grep command with the -r option recursively searches all directories starting from the current directory (.). The --include option limits the search to files that match the specified pattern, in this case, files that end with "WhatToDo.txt":
~~~
$ grep -rilE "hike|hiking|climbing" --include="*WhatToDo.txt" .
written_2/travel_guides/berlitz2/Bali-WhatToDo.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
written_2/travel_guides/berlitz2/Berlin-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
~~~
### Citation:
[Source used for various `grep` options](https://man7.org/linux/man-pages/man1/grep.1.html)
