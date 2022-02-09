## 2021-11-18:

[
    A _bounce_ is a single-page session on your site.
](https://support.google.com/analytics/answer/1009409?hl=en)

Latency is a known cause of increased bounce rate in the sense that a human
checking your website may become impatient while waiting for a web page to
render and decide to leave. In some circumstances it makes sense to include
_bounce rate_ as part of your observability pattern.


## 2021-11-17:

It is important to keep in mind the latency associated with retrieving
data from memory vs the latency of retrieving data from disk. The chart
below helps at visualizing and memorizing some of important latencies
like, for example, the latency of a network round-trip within the same
datacenter compared to the latency across continents and oceans.

https://colin-scott.github.io/personal_website/research/interactive_latency.html


## 2021-11-15:

On recent versions of Red Hat Enterprise Linux and similar distribution, if
`man -k <something>` shows a `nothing appropriate` message as shown below:
```shell
$ man -k man
man: nothing appropriate.
```
The root usercan easily fix that with `mandb -c` as shown:

```
# mandb -c
Processing manual pages under /usr/share/man/overrides...
Updating index cache for path `/usr/share/man/overrides/man8'. Wait...done.
Checking for stray cats under /usr/share/man/overrides...
Checking for stray cats under /var/cache/man/overrides...
Processing manual pages under /usr/share/man...
Updating index cache for path `/usr/share/man/man5'. Wait...mandb: can't open /usr/share/man/man5/regulatory.bin.5.gz: No such file or directory
mandb: warning: /usr/share/man/man5/regulatory.db.5.gz: bad symlink or ROFF `.so' request
Updating index cache for path `/usr/share/man/man1'. Wait...mandb: warning: /usr/share/man/man1/gdk-pixbuf-query-loaders.1.gz: whatis parse for gdk-pixbuf-query-loaders(1) failed
Updating index cache for path `/usr/share/man/man3'. Wait...mandb: warning: /usr/share/man/man3/function::fp_div.3stap.gz: whatis parse for function::fp_div(3stap) failed
mandb: warning: /usr/share/man/man3/function::sa_handler.3stap.gz: whatis parse for function::sa_handler(3stap) failed
mandb: warning: /usr/share/man/man3/probe::sunrpc.svc.authorise.3stap.gz: whatis parse for probe::sunrpc.svc.authorise(3stap) failed
mandb: warning: /usr/share/man/man3/function::-.3stap.gz: whatis parse for function::-(3stap) failed
mandb: warning: /usr/share/man/man3/function::MKDEF.3stap.gz: whatis parse for function::MKDEF(3stap) failed
mandb: warning: /usr/share/man/man3/Net::libnetFAQ.3pm.gz: whatis parse for Net::libnetFAQ(3pm) failed
Updating index cache for path `/usr/share/man/mann'. Wait...done.
Checking for stray cats under /usr/share/man...
Checking for stray cats under /var/cache/man...
Processing manual pages under /usr/share/man/overrides...
Updating index cache for path `/usr/share/man/overrides/man8'. Wait...done.
Checking for stray cats under /usr/share/man/overrides...
Checking for stray cats under /var/cache/man/overrides...
Processing manual pages under /usr/share/man/ru...
Updating index cache for path `/usr/share/man/ru/man7'. Wait...done.
Checking for stray cats under /usr/share/man/ru...
Checking for stray cats under /var/cache/man/ru...
Processing manual pages under /usr/share/man/hu...
Updating index cache for path `/usr/share/man/hu/man8'. Wait...done.
Checking for stray cats under /usr/share/man/hu...
Checking for stray cats under /var/cache/man/hu...
Processing manual pages under /usr/share/man/ja...
Updating index cache for path `/usr/share/man/ja/man7'. Wait...done.
Checking for stray cats under /usr/share/man/ja...
Checking for stray cats under /var/cache/man/ja...
Processing manual pages under /usr/share/man/fr...
Updating index cache for path `/usr/share/man/fr/man7'. Wait...done.
Checking for stray cats under /usr/share/man/fr...
Checking for stray cats under /var/cache/man/fr...
Processing manual pages under /usr/share/man/it...
Updating index cache for path `/usr/share/man/it/man8'. Wait...done.
Checking for stray cats under /usr/share/man/it...
Checking for stray cats under /var/cache/man/it...
Processing manual pages under /usr/share/man/pl...
Updating index cache for path `/usr/share/man/pl/man5'. Wait...done.
Checking for stray cats under /usr/share/man/pl...
Checking for stray cats under /var/cache/man/pl...
Processing manual pages under /usr/share/man/ko...
Updating index cache for path `/usr/share/man/ko/man8'. Wait...done.
Checking for stray cats under /usr/share/man/ko...
Checking for stray cats under /var/cache/man/ko...
Processing manual pages under /usr/share/man/sk...
Updating index cache for path `/usr/share/man/sk/man8'. Wait...done.
Checking for stray cats under /usr/share/man/sk...
Checking for stray cats under /var/cache/man/sk...
Processing manual pages under /usr/share/man/cs...
Updating index cache for path `/usr/share/man/cs/man3'. Wait...done.
Checking for stray cats under /usr/share/man/cs...
Checking for stray cats under /var/cache/man/cs...
Processing manual pages under /usr/share/man/da...
Updating index cache for path `/usr/share/man/da/man8'. Wait...done.
Checking for stray cats under /usr/share/man/da...
Checking for stray cats under /var/cache/man/da...
Processing manual pages under /usr/share/man/de...
Updating index cache for path `/usr/share/man/de/man8'. Wait...done.
Checking for stray cats under /usr/share/man/de...
Checking for stray cats under /var/cache/man/de...
Processing manual pages under /usr/share/man/id...
Updating index cache for path `/usr/share/man/id/man5'. Wait...done.
Checking for stray cats under /usr/share/man/id...
Checking for stray cats under /var/cache/man/id...
Processing manual pages under /usr/share/man/pt_BR...
Updating index cache for path `/usr/share/man/pt_BR/man8'. Wait...done.
Checking for stray cats under /usr/share/man/pt_BR...
Checking for stray cats under /var/cache/man/pt_BR...
Processing manual pages under /usr/share/man/sv...
Updating index cache for path `/usr/share/man/sv/man7'. Wait...done.
Checking for stray cats under /usr/share/man/sv...
Checking for stray cats under /var/cache/man/sv...
Processing manual pages under /usr/share/man/tr...
Updating index cache for path `/usr/share/man/tr/man7'. Wait...done.
Checking for stray cats under /usr/share/man/tr...
Checking for stray cats under /var/cache/man/tr...
Processing manual pages under /usr/share/man/zh_CN...
Updating index cache for path `/usr/share/man/zh_CN/man8'. Wait...done.
Checking for stray cats under /usr/share/man/zh_CN...
Checking for stray cats under /var/cache/man/zh_CN...
Processing manual pages under /usr/share/man/zh_TW...
Updating index cache for path `/usr/share/man/zh_TW/man8'. Wait...done.
Checking for stray cats under /usr/share/man/zh_TW...
Checking for stray cats under /var/cache/man/zh_TW...
Processing manual pages under /usr/share/man/es...
Updating index cache for path `/usr/share/man/es/man1'. Wait...done.
Checking for stray cats under /usr/share/man/es...
Checking for stray cats under /var/cache/man/es...
Processing manual pages under /usr/share/man/uk...
Updating index cache for path `/usr/share/man/uk/man1'. Wait...mandb: warning: /usr/share/man/uk/man1/dos2unix.1.gz: whatis parse for dos2unix(1) failed
mandb: warning: /usr/share/man/uk/man1/dos2unix.1.gz: whatis parse for mac2unix(1) failed
mandb: warning: /usr/share/man/uk/man1/dos2unix.1.gz: whatis parse for unix2dos(1) failed
mandb: warning: /usr/share/man/uk/man1/dos2unix.1.gz: whatis parse for unix2mac(1) failed
Updating index cache for path `/usr/share/man/uk/man7'. Wait...done.
Checking for stray cats under /usr/share/man/uk...
Checking for stray cats under /var/cache/man/uk...
Processing manual pages under /usr/share/man/ca...
Updating index cache for path `/usr/share/man/ca/man5'. Wait...done.
Checking for stray cats under /usr/share/man/ca...
Checking for stray cats under /var/cache/man/ca...
Processing manual pages under /usr/share/man/nl...
Updating index cache for path `/usr/share/man/nl/man1'. Wait...done.
Checking for stray cats under /usr/share/man/nl...
Checking for stray cats under /var/cache/man/nl...
Processing manual pages under /usr/share/man/pt...
Updating index cache for path `/usr/share/man/pt/man8'. Wait...done.
Checking for stray cats under /usr/share/man/pt...
Checking for stray cats under /var/cache/man/pt...
Processing manual pages under /usr/local/share/man...
Updating index cache for path `/usr/local/share/man/mann'. Wait...done.
Checking for stray cats under /usr/local/share/man...
Checking for stray cats under /var/cache/man/local...
126 man subdirectories contained newer manual pages.
8842 manual pages were added.
0 stray cats were added.
```


## 2021-11-11: Object Orientation is more important than ever.

I need refreshers of all the following:
- Unix signals.
- The boot process.
- Differences between RHEL 6, 7 & 8.
- Memory management algorithms in Python.


# 2021-11-10: Create and see zombie processes.

Technically, zombie processes are not processes because they are not programs being executed.

Zombie processes are entries in the process table associated with processes that completed their execution and no longer exist.

If you are lucky you may be able to detect a zombie process by running tools like `ps` or `top`. If you are not lucky, then you can create some and see their Process Identification numbers (PIDs) as follows:

First, on a terminal windows, run the following shell command:

```bash
while true ; do ps axo pid=,stat= | awk '$2~/^Z/ { print $1, $2 }' ; done
```

The above command is simply an infinite loop around the following `ps axo pid=,stat= | awk '$2~/^Z/ { print $1 }'`. The`ps` there list the PIDs and status of processes, which are then passed to `awk` to print the PIDs only of those processes whose status starts with 'Z' (i.e. zombie processes).

Leave that running and on another terminal window build the following C code:

```
/* File: zombies.c
   Compile: make zombies
   Run: ./zombies
   Source: Wikipedia */

#include <sys/wait.h>
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int main(void)
{
    pid_t pids[10];
    int i;

    for (i = 9; i >= 0; --i) {
        pids[i] = fork();
        if (pids[i] == 0) {
            printf("Child%d\n", i);
            sleep(i+1);
            _exit(0);
        }
    }

    for (i = 9; i >= 0; --i) {
        printf("parent%d\n", i);
        waitpid(pids[i], NULL, 0);
    }

    return 0;
}
```

When run, the program will take a few seconds to execute. While it runs, you will be able to see the PIDs of zombie processes displayed on the other window (note the simple script above does show repeated PIDs as it runs)

 Credits go to [Wikipedia for the C code](https://en.wikipedia.org/wiki/Zombie_process#Example) and [Askubuntu for the ps-to-awk pipe](https://askubuntu.com/questions/111422/how-to-find-zombie-process).


## 2021-11-09: Orphan processes.

Generally, a process whose original parent terminated is called an *orphan* process.

In Unix-like operating systems processes are created by processes that call the `fork()` system call.

When a process creates another process, their parent-child relationship is tracked in process table. The spawned process is called the *child* process while the process that called `fork()` is called the *parent* process. Each process has exactly one parent.

When a parent process terminates, the child process is often, but not always, immediately re-parented to the special `init` process and called an *orphan*.


## 2021-11-08: Object Orientation is more important than ever.

To be a successful software developer, you need to have thorough
understanding of object orientation.

Some of the most important relationships between objects are:

**Inheritance**: when an object is a (*is-a*) of a certain type.

**Association**: when an object has a (*has-a*) relationship with other
object or objects. Objects are independent in their lifecycles.

**Aggregations**: is a special form of association where all the related
objects are *owned*. Nevertheless, the lifetimes of the objects are
independent. (*whole-part* and *a-part-of* apply instead of *has-a*)

**Composition**: is a special form of aggregation where the owned object
have dependent lifecycles.


## 2019-05-30: What type is that (unmounted) file system?

On [2019-04-17](https://github.com/rjimeno/today_i_learned#2019-04-17) I wrote about a neat way to obtain the type of a file system __that is already mounted__. That's not the only way, but it is a neat one. The problem with it is that it requires the file system to be mounted and, the core problem is that, sometimes we do not know the type of a file system that we want to mount and it is for that reason that we cannot mount it; kind-of chicken-and-egg problem!

There is an elegant solution to that: Turns out the ```file``` command can find out the type of a file system as follows:

```bash
$ sudo file -s /dev/sda1
```

Where ```/dev/sda1``` represents the partition whose file system type is unknown. Alternatively,

```bash
$ lsblk -f
```

should also list the file system types of all the block devices.


## 2019-05-17: Input from files named in command line arguments or standard input.

Earlier today, I finished writing a script that required two arguments being passed on the command line. The script was, in essence, a *reducer* or some form of filter that would summarize information. Its input would be taken exclusively from standard input.

Once the script was done, I realized the script would be more useful and comfortable to handle if input could be read from files with names provided in the command line. Anything after the first pair of arguments would be assumed to be the name of a file and an open() operation would be attempted immediately followed by the reading of all of their contents. Last but not least, an attempt to read from actual stdin until no more input is available.

Since I was in no mood to carefully change significant parts of my code, I searched the Internet for Python libraries to help me and found `fileinput` which provided me with functionality similar to the one I usually enjoy from the diamond operator when programming Perl.

An excerpt of my code using it follows:

```python
import fileinput

for line in fileinput.input(argv[3:]):
        tmp = line.rstrip().split(',')
        if 10 != len(tmp):
            continue  # That line was probably malformed.
```


## 2019-05-16: @ times, Python 2 != Python 3 ; part 2 of 2.

I wrote a script that reads log files that have a timestamp in the form of a number of seconds since epoch as a floating point number and tested it with a tiny log file. My initial implementation aimed at Python 3. Tests found records within a second of 2017-05-05T03:25:01.

Then, I added support for Python 2 but found its records at a different time mark: 2017-05-05T07:25:01; that's 4 hours later! The time difference seemed to me due to the way time zones are interpreted. Considering that, it makes sense to use set the TZ environment variable as follows:

```
$ # The given TIME is in UTC for Python 3.
$ TZ=UTC   python3 failed_requests.py  2017-05-05T07:25:01.63 2017-05-05T07:25:01.67 log_sample.txt
Between time   2017-05-05T07:25:01.630000   and time   2017-05-05T07:25:01.670000  :
player.refinitiv.com returned 33.33% 5xx errors.
refinitiv.com        returned 40.00% 5xx errors.

$ # The given FILE has timestamps corresponding to UTC-5 for Python 2.
$ TZ=UTC-5 python2 failed_requests.py  2017-05-05T07:25:01.63  2017-05-05T07:25:01.67 log_sample.txt
Between time   2017-05-05T07:25:01.630000   and time   2017-05-05T07:25:01.670000  :
player.refinitiv.com returned 33.33% 5xx errors.
refinitiv.com        returned 40.00% 5xx errors.
```


## 2019-05-15: @ times, Python 2 != Python 3 ; part 1 of 2.

I wrote a script that checks a timestamp (from a file) to be "sandwiched" between two other timestamps given by the user. The script uses libraries to do most of the work including conversions from date times represented with ISO 8601 date times using strings, to timestamps in seconds using floating point notation.

Observe that some of those calculations are non-trivial and involve leap years, time zones, daylight savings and even leap seconds. While those calculations are performed by the libraries with Python 3, Python 2 misses some functionality and I had to implement my own calculations as shown in the following excerpt code:

```python
from datetime import datetime
from sys import argv, stdin, version_info
from dateutil import parser

...

def get_ts(date_time):
    """
    Calculates a timestamp differently depending on Python's version.
    """
    if version_info[0] <= 2:
        return (date_time - datetime(1970, 1, 1, tzinfo=None)).total_seconds()
    # If Python's major version is 3 or above, use the more precise .timestamp()
    return date_time.timestamp()

def main():
    start_time, end_time = get_datetimes_checked()
    for line in stdin:
        timestamp, host, message = line.rstrip().split(',')
        if get_ts(start_time) <= timestamp < get_ts(end_time):
            # Do something interesting with host & message information.
```
Observing the sample above it becomes clear that Python 3 uses `date_time.timestamp()` but since Python 2 has no `.timestamp()` method, it is approximated with `(date_time - datetime(1970, 1, 1, tzinfo=None)).total_seconds()` for Python 2. Unfortunately, even for dates that are as close as only a couple of years apart, the precision on the implementation of both methods differ by a fraction of a second.


## 2019-05-14: Attach a tab to iTerm2.

Deattaching an iTerm2 tab from a window so it can exist in a different, and possibly new window, is easy: You place the pointer on top of the tab and grab the tab out of the window to its new location. The dragging is done by pressing (without releasing), then dragging.

Attaching an independent tab or window is useful when you have too many windows and it makes sense to organize them in fewer windows with tabs. To do this, you also grab, then move to the window that will collect a new tab. The tricky part is that keeping the pointer pressed will not move the window **unless** you press the key combination <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>⌘</kbd> (or a similar equivalent depending on your operating system), then pressing the pointer and grabbing to insert the tab into the new location.

A useful animation and *micro*rticle about that is available as [iTerm2 - merge a pane back to window or tab bar](http://azaleasays.com/2014/03/05/iterm2-merge-a-pane-back-to-window-or-tab-bar/).


## 2019-05-13: Bridge Python to its past with __future__.

I generally like to write for version 3 of Python so I can take advantage of features like the improved division, the print function (vs print statement) and even the f-strings. To do so, I hint (almost enforce) the Python 3 by starting my scripts with the following shebang line `#!/usr/bin/env python3`. That way, scripts with execution permission will attempt to use a version 3 over any version 2 in case more than one version is available.

Whenever possible, I try not to forbid the use of Python 2 but, instead, try to write code that works correctly on both. One way to achieve that is by importing the `__future__` library. That way, Python 2 will be provided with a print function just like the one on Python 3. Similarly, the division (/) on Python 2 will behave as the division in Python 3. That really simplified my work of making code that was initially written for version 3 work with version 3.

There are times though, when `__future__` does not solve my problem. Those times I use a conditional statement to check for the version numbers stored in sys.version_info[] and conditionally execute code accordingly. The following code is not very useful, but should exemplify this principle:

```Python
#!/usr/bin/env python3

"""
Works much better with Python 3 rather than 2.
Experiment by replacing the searched number (EULER7)
and limit (EULER10) with a larger combination like
EULER10 & CLAUSEN or CLAUSEN & LUCAS to compare
their performance and whether they run successfully
or exhaust memory (or your patience) in the process.
"""

import __future__
import sys

CATALDI = 524287
EULER7 = 6700417
EULER10 = 2147483647
CLAUSEN = 67280421310721
LUCAS = 170141183460469231731687303715884105727

if sys.version_info[0] <= 2: # xrange() is needed.
  print(EULER7 in xrange(CATALDI, EULER10 + 10))
# Version 3 does not have (nor need) xrange().
print(EULER7 in range(CATALDI, EULER10 + 1))
# Version 3 works quickly with CLAUSEN and maybe LUCAS.
```


## 2019-05-08: `tail -r | tail | tail -r` is better than `head`.

When comparing the Unix utilities `head` and `tail`, seems apparent that `tail` has more and better features than `tail` does. For example, `tail` can do its work counting relative to the beginning of the input whereas `head` can *not* do its work counting relative to the end of the input.

A clever workaround is to invert the file you want to work with, then feed it to tail and finally invert the result again. That should be equivalent as having `head` being capable of doing its work counting relative to the end of the input. Example:

```$ tail -r < /etc/passwd | tail -n +2 | tail -r > passwd-except-last-two-lines  # As if 'head -n +2 ' was valid.```


## 2019-05-07: `browsh` is really promising, but it is not mature enough just yet.

I have been trying to write a Python script that scraps a few values from an HTML document after performing a non-trivial Single Sign-On (SSO) exchange between third parties. I felt one way to get there would be to use tools like `wget` and `curl` to fetch the said HTML document.

Since neither of those tools seems capable of performing anything besides simple authentication, I started exploring the current state of text-based web browsers. My research showed that Lynx, W3m, and ELinks are in great shape. Each has distinctive features with their implicit strengths and weaknesses.

Browsh seems too good to be true, but I'm still evaluating it. I believe Browsh is not *really* a text-based web browser because it depends on Firefox, but I'm not sure just yet as its failed for me on a RedHat Linux system running inside VirtualBox on my Mac (via SSH).


## 2019-05-06: Better *done* than *perfect*.

I first learned about Browsh a few days ago and I wanted to write something about it here. Since I did not know exactly what to write and I did not know enough about Browsh, I postponed it "only one day" for many days, and that is not good.

I should always keep in mind that it is often better to do something imperfect and, maybe, improve on it later if it is useful and worth it. By following that path it is possible to approach perfection in a way that is probably more enjoyable than by trying to approach perfection too early on.


## 2019-04-29: Screen recording with audio.

On a Mac, recording your screen as you speak (for example, to teach a recorded computer-based class), is very simple: You can start quick time as it is already included with the Mac OS, and then select File -> New Screen Recording.

A Screen Recording window will appear and to the right of the recording button (red, at center), select the pull-down so you can choose External Microphone from the list of Microphones. By default, None is selected and that will give you a silent video.

In Google Drive, uploading a 20-minute video created in this way should take approximately 80 minutes.


## 2019-04-25: Markdown.

In Markdown (.md) files, to create *slant* effect, surround with
asterisks or underscore (* or _). For __bold__ effect, surround with
double asterisks or underscores (** or **).

So far, my two favorite Markdown cheat-sheets are:

https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#links

and

https://github.com/tchapi/markdown-cheatsheet/blob/master/README.md


## 2019-04-22: Managing vs leading.

What's the difference between managing and leading?

Pamela Rucker reports that John Carter, from Hardvard Busines School, has the following opinion:

Managing, is about dealing with complexity whereas leading, is about dealing with change.


## 2019-04-21: CFEngine.

CFEngine seems to be the first modern or contemporary Configuration
Management tool.

I found very interesting information for it on
Wikipedia although there is currently a warning there regarding
single-source information.

Finally, I need to find time to read the 1998 paper [Computer
Immunology](https://www.usenix.org/legacy/publications/library/proceedings/lisa98/full_papers/burgess/burgess.pdf)
(from a Usenix's LISA conference) as it seems to be important.



## 2019-04-20: Gather information on installed SSD or HDD.

In Linux, there are multiple ways to find out if a disk spins or is
solid-state instead. Some of the tools that can be used are `lsblk`,
`lshw`, `smartctl`, and the simplest of all, `cat`.

For detailed information, check the manual pages for each tool. Use
the following examples as a guide keeping in mind that some may
require to be run by the root user. sda and /dev/sda in the examples
should be replaced by your device.

```bash
$ cat /sys/block/sda/queue/rotational # Will display 0 for SSD.
```

or

```bash
$ lsblk -b -o name,rota  # Under the ROTA column, 0 means SSD.
```

or

```bash
$ lshw -short -class disk  # May need root to get all the info.
```

or

```bash
$ sudo smartctl -a /dev/sda  # Will probably fail on a virtual machine.
```



## 2019-04-19:

Building on knowledge from yesterday and addressing a question I was
not able to answer successfully a few years ago (while working for
Delivery.com). If you need to "recover" file that was deleted, there
good hope as long as a running process keeps it open.

As an example, imagine that you deleted a file that you need to
recover and that `lsof +L1` helps you find out the PID of that keeps
it open is `12345`. Then you will do:

```bash
$ ls -l /proc/12345/fd/*
```

And observe that one of those file descriptors point to the file you
want to recover. Let us suppose the file descriptor here is `4` and
so your next command will be:

```bash
$ cp /proc/11230/fd/ recovered_file
```

Once `cp` is done, the file named `recovered_file` will have the same
same content as the file that was deleted. It may be relevant to
note here that if we are working with large files in a small file
systems you may need to get creative on where to put them so they
fit.



## 2019-04-18:

In Linux, `+L1` is the only option that is needed to have `lsof`
report files that have been "deleted" and are still open. This is
useful because sometimes a file system is out of space even though
tools like `du` report utilization that is under capacity.

With the command `lsof +L1` you can get a list of all the files in
the current file system with zero link counts. In other words, a list
of the files that have no name. You can also think of those as files
with zero links or, equivalently, files that have been deleted.

Still, in Linux and probably others OO SS (Solaris for example),
issuing `lsof | grep deleted` should also show deleted files but
feels more prone to errors. For example, a script would probably
fail if the file name or path include the string 'deleted'.



## 2019-04-17:

In Linux, `df -T` also displays the type of a file system.

*Update: on [2019-05-30](https://github.com/rjimeno/today_i_learned/blob/master/README.md#2019-05-30-what-type-is-that-unmounted-file-system) I learned a way to display the type of a file system that is __not__ mounted.*


## 2019-03-17:

GDB does not run on an Apple's OS X until after you have "codesigned"
it. One way to go about that is described in the following URL:
https://gist.github.com/hlissner/898b7dfc0a3b63824a70e15cd0180154

The instructions that follow here are copied from there:
> Note: these instructions are for pre-Sierra MacOS. Sierra Users: see
https://gist.github.com/gravitylow/fb595186ce6068537a6e9da6d8b5b96d
by @gravitylow.

If you are getting this in gdb on OSX while trying to run a program:

```
Unable to find Mach task port for process-id 57573: (os/kern) failure (0x5).
 (please check gdb is codesigned - see taskgated(8))
```

1. Open Keychain Access
2. In the menu, open **Keychain Access > Certificate Assistant >
Create a certificate**
3. Give it a name (e.g. `gdbc`)
    + Identity type: Self Signed Root
    + Certificate type: Code Signing
    + Check: let me override defaults
4. Continue until it prompts you for: "specify a location for..."
5. Set Keychain location to System
6. Create a certificate and close assistant.
7. Find the certificate in System keychains, right click it > get
info (or just double click it)
8. Expand **Trust**, set **Code signing** to `always trust`
9. Restart taskgated in terminal: `killall taskgated`
10. Enable root account:
    1. Open System Preferences
    2. Go to User & Groups > Unlock
    3. Login Options > "Join" (next to Network Account Server)
    4. Click "Open Directory Utility"
    5. Go up to **Edit > Enable Root User**
11. Run `codesign -fs gdbc /usr/local/bin/gdb` in terminal: this asks
for the root password
12. Disable root account (see #10)

Done!


## 2019-03-15:

Udacity's [Computer Networking - Security and Software Defined
Networking, by Georgia Tech (UD436)]
(https://www.udacity.com/course/computer-networking--ud436) is an
excellent course!

Personally, it reminded me a lot of material that I forgot from
Computer Networking courses I took in the past. I also learned a few
things that are new or have developed relevance within the past
decade like, for example,  Software Defined Networks.

## 2019-05-08: Sharing "future" timestamps from Jenkins 2 using a scripted Jenkinsfile pipeline; part 2 of 2.

In my previous post from [2019-03-05](https://github.com/rjimeno/today_i_learned/blob/master/README.md#2019-03-05-sharing-future-timestamps-from-jenkins-2-using-a-scripted-jenkinsfile-pipeline-part-1-of-2) I showed a Jenkinsfile that creates two files named TODAY.txt and TOMORROW.txt whose content is a 15-digit timestamp with the form YYYYMMddHHmmss where YYYY is the year, MM: the month, dd: day of the month, HH: 0 to 23 hours of the day, mm: 0 to 59 minutes in each hour, ss: 0 to 59 or 60 seconds in a minute.

That Jenkinsfile is good because it can be deployed by a regular user without requiring approval from an administrator on most (probably all) Unix-like Jenkins hosts. On the other hand, its code is long-winded and cumbersome. For more than one reason it is not good enough for large scale deployments where multiple executions would, most probably, "step on each other" and break havoc.

One of my coworkers proposed a better solution that required very few changes. So far, the only downsides I see are that it does require approval from an administrator (as static methods are not allowed on Jenkin's Groovy) and that it does not entirely run on non-Unix systems yet. Here's the code:

```Jenkinsfile
#!/usr/bin/env groovy

// Jenkins Scripted Pipeline by Roberto Jimeno shows a way to get tomorrow's
// date and use it from Groovy.

// This function is not used but put here to show formatting ISO-style.
def post_alarm(body) {
    String data = dataForCurl(body, '')
    def iso_today   =temp_date.format("YYYY-MM-ddTHH:mm:ss.000Z")
    def iso_tomorrow=temp_date.format("YYYY-MM-ddTHH:mm:ss.000Z")
}

node {
    stage('Create time stamp.') {
        def timestamp_today = new Date()
        def timestamp_tomorrow = timestamp_today.next()
        def today=timestamp_today.format("YYYYMMddHHmmss")
        def tomorrow=timestamp_tomorrow.format("YYYYMMddHHmmss")
        println today + " == today."
        println tomorrow + " == tomorrow."
        sh 'echo ${today} > TODAY.TXT'  // Fails on Windows; comment-out.
        sh 'echo ${tomorrow} > TOMORROW.TXT'  // Fails on Windows.
    }
}
```


## 2019-03-05: Sharing "future" timestamps from Jenkins 2 using a scripted Jenkinsfile pipeline; part 1 of 2.

Last year I wrote a Jenkinsfile that, for reasons that I can't remember anymore, required a couple of timestamps to be shared. I remember thinking of using environment variables as well as temporary files, but can't recall all my reasoning for deciding on the latter.

Along the development path, I collected idiocracies, and my solution became cumbersome. Once my code solved the problem effectively (and not necessarily, efficiently), was vetted by my teammates, and got merged into a master branch, I patiently waited to seize an opportunity to improve it.

The following code summarizes and exhibits the core components I want to address. All further comments don't appear here but in [2019-03-08](https://github.com/rjimeno/today_i_learned/blob/master/README.md#2019-05-08-sharing-future-timestamps-from-jenkins-2-using-a-scripted-jenkinsfile-pipeline-part-2-of-2) instead.

```Jenkinsfile
#!/usr/bin/env groovy

// Jenkins Scripted Pipeline by Roberto Jimeno shows a way to get tomorrow's
// date and use it from Groovy.

// The core of this trick is to use “date -d '+1 day'” to get tomorrow’s date
// on GNU systems (v.g. Linux) or “date -v+1d” many other systems (like OS X).

// Following pair of environment variables will be used later.
env.utc_today=''
env.utc_tomorrow=''

// This function is not used but put here to show formatting ISO-style.
def post_alarm(body) {
    String data = dataForCurl(body, '')

    sh """
        iso_today=\$(date -u +%Y-%m-%dT%H:%M:%S.000Z)
        iso_tomorrow=\$(date -d "+1 day" -u +%Y-%m-%dT%H:%M:%S.000Z)
    """
}

node {
    stage('Create time stamp.') {
        env.utc_today = sh (
                script: 'date -u +%Y%m%d%H%M%S',
                returnStdout: true
        ).trim()
        env.utc_tomorrow = sh (
                script: 'date -d "+1 day" -u +%Y%m%d%H%M%S',
                returnStdout: true
        ).trim()
        println env.utc_today
        println env.utc_tomorrow
        sh 'date -u +%Y%m%d%H%M%S > TODAY.txt'
        sh 'date -d "+1 day" -u +%Y%m%d%H%M%S > TOMORROW.txt'
    }
}
```


## 2019-02-22:

On a Mac (running OS X or MacOS), Vagrant can be installed using
Homebrew using the following command:

```bash
$ brew cask install vagrant
```

The `brew install` commands without `cask` typically install somewhat
simple, command-line software distributed under some FOSS license. In
contrast, `brew cask install` commands can be used to install more
complex software, that has or interacts with a GUI and that is
licensed under some form of proprietary license.



## 2019-02-21:

By accident, I came across the executable binary file
`/usr/bin/sigdist.d` on my Mac and that lead me to `man sigdist.d`
which in turn sent me to Safari Books Online for the book DTrace:
Dynamic Tracing in Oracle and so I'm beginning to learn that DTrace is
a powerful tool that can help me performance-tune software and
systems.

Just put a bunch of material in a queue and I'll start reading once I
have some availability.
